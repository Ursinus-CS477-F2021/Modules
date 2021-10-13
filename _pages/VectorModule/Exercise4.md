---
layout: exercise_pyodide
permalink: "VectorModule/Exercise4"
title: "CS 477: Vector Module: High Dimensional Dot Products in Numpy"
excerpt: "CS 477: Vector Module: High Dimensional Dot Products in Numpy"
canvasasmtid: "129632"
canvaspoints: "1.5"
canvashalftries: 5

info:
  comments: "true"
  prev: "./Video4"
  next: "./Video5"
  points: 1.5
  instructions: "<p>Fill in the code below to compute the dot product between two vectors in arbitrary dimensions.</p>"
  packages: "numpy"
  goals:
    - Implement vector operations on high dimensional vectors in numpy
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    feedback.setValue(pyodide.globals.res);
  correctcheck: |
    pyodide.globals.res == "12.141875500718468.12.36565070207807.10.198940720598285.5.068628568068711.-2.468893864937528.3.9150637481612796.12.778494901042718.6.652365351170923.-0.706076987359809.-15.148029337768001"
  incorrectchecks:
    - incorrectcheck: |
        pyodide.globals.res == "0.0.0.0.1.1.0.1.0.1"
      feedback: "Try again.  You're close!  You just have your answer flipped"
    - incorrectcheck: |
        pyodide.globals.res == "0.0.0.0.0.0.0.0.0.0"
      feedback: "Try again.  It looks like you're always returning 0 for the dot product, but this is only true if the vectors are orthogonal."
    - incorrectcheck: |
        pyodide.globals.res == "3.484519407424569.3.516482717443393.3.1935780436053673.2.251361492090666.nan.1.9786520027941445.3.5747020716477502.2.579217972791544.nan.nan"
      feedback: "Try again.  Careful!  It looks like you're taking the square root of the dot product, but you don't need to do that."

files:
  - filename: "Student Code"
    name: driver
    ismain: false
    isreadonly: false
    isvisible: true
    height: 500
    code: | 
          import numpy as np

          def get_dotproduct(a, b):
              """
              Compute the dot product between two high dimensional vectors

              Parameters
              ----------
              a: ndarray(d)
                Vector a
              b: ndarray(d)
                Vector b
              
              Return
              ------
              0 if v is closer to a and 1 if vector is closer to b
              """
              res = 0
              ## TODO: Fill this in
              return res



  - filename: "Test Code Block"
    ismain: true
    name: main
    isreadonly: true
    isvisible: true
    code: |
        np.random.seed(0)
        res = ""
        d = 100
        for i in range(10):
          a = np.random.randn(d)
          b = np.random.randn(d)
          res = "{}{}.".format(res, get_dotproduct(a, b))
        res = res[0:-1]
---