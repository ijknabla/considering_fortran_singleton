# considering_fortran_singleton
What is the best implementation of singleton???

## Premise
Consider how Fortran can implement singleton and which methods are better.

I do not focus on whether singleton is effective in software design or not,
especially about numerical calculation which is Fortrans part.

However, I explain my opinion of singleton merit in Fortran to clarify my motivation.

### My Opinion about singleton in Fortran

Fortran is not fully object-oriented language.
Almost all data are `INTEGER(4)` `REAL(8)` `COMPLEX(8)`.
Fortran90 does not have class. But Fortran90 can define
overloaded function and can define user defined operator and assignment.
These features are different from C++ or Java. Fortran90 will
conclude another answer.

Fortran's I/O resource management is out-of-date. 
'unit number' is a shared resouece of the process being executed,
and this specification itself potentially closely couples the I/O functions
of all the modules. A singleton that uniquely manages 'unit number' is essential.

And also think about __legacy__ codes.
They are collections of messed upped COMMON statement. 
Even if singleton is bad solution,
singleton will be more effective than COMMON statement.