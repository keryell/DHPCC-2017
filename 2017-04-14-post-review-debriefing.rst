2017/04/14, 13h

Meeting to decide what to do.


REVIEW 2

  It's mentioned that SYCL supports C++14/17 (this is true for the
  SYCL 2.2 provisional specification but not for the SYCL 1.2
  specification), it would be good to clarify this.

Addressed.

  When describing the OpenCL interoperability from SYCL to OpenCL, the
  accessor class is used as an example, however this interoperability
  feature is not supported for the accessor class.

Clarify.

BUT ACTUALLY SUBMIT A BUG TO CLARIFY THIS.

  In the second sample code the SYCL buffers should have a dimension
  template parameter.

https://cvs.khronos.org/bugzilla/show_bug.cgi?id=16317

  In the future work section it would be good to mention PACXX and
  ParallelSTL as they are very related works.

Not clear if it is related, because it is not about OpenCL interoperability.

  "taking advantage of OpenMP simplicity and type safety" - maybe
  reword this slightly, this sounds as though SYCL is based on OpenMP.

Done.

  "the shared memory between the host and devices" -> "the shared
  virtual memory between the host and devices"

Done.


REVIEW 4

  Given the GPU example, it is not completely obvious whether the pure
  OpenCL version is using the proposed SYCL OpenCL coding style, or
  actually pure OpenCL using conventional host code---i.e. define
  'pure'. The text/caption could be clearer here.

Done.

  Assuming it is the proposed OpenCL wrapper use of SYCL, it also
  provides a performance gain. Which would mean it is beneficial to
  not use SYCL for the kernel code, but that conclusion is not
  drawn. It would be interesting to also have the numbers for a
  conventional OpenCL implementation, using the C-API or the official
  OpenCL C++ wrapper with explicit memory transfers. Maybe showing the
  triSYCL version with redundant data transfers, is somehow related to
  that, otherwise its point remains completely unclear to this
  reviewer.

TODO?

  The question remains: Regarding both, programmability, and
  performance, should I use a) SYCL with inline code, b) SYCL with
  OpenCL kernel code, or c) pure OpenCL (i.e. no SYCL at all)? After
  listing all the advantages of SYCL in section 2, I would assume
  (a). But the paper presents (b), and provides arguments over (c). So
  what about (a) vs. (b). Is the proposed use of SYCL a compromise for
  OpenCL programmes where going the last step towards (a),
  i.e. rewriting the kernel code as SYCL, is not an option? Or is
  there a performance argument?

Done.

  The second application section addressing FPGAs is missing due to IP
  issues. The related work section is a bit hard to read due to
  language issues. After reading the whole paper sequentially, I would
  recommend other readers to start with the Conclusion, which provides
  a clear summary of the paper's content.

Done.


REVIEW 5

  Although, the title and some parts of the paper emphasizes C++17,
  not too much proposed C++17 features are used or referred by the
  article.

Done.


REVIEW 6

  There is not much of any analysis into what causes performance
  differences.

Not enough time for this deadline unfortunately.

  Also a paragraph in the description is confusing: "Note
  that since current triSYCL[10]cannot target GPU yet and the
  community edition version of ComputeCpp[4] cannot run yet on our
  Linux distribution, we cannot compare the results against the normal
  pure SYCL code running on GPU."
  a) What is ComputeCPP? It is the only time it is mentioned in the
     paper.

Clarified.

  b) Doesn't figure 4 show a comparison on GPU?
  c) If non of the three bars in fig 4 is the normal SYCL version what
     are they??

Clarified with a newer experiment.

  All in all me opinion is that this paper doesn't enhance the
  discussions around SYCL by much. It would certainly need to be
  reworked to contain less SYCL explanation and more analysis of the
  implemented codes and the results obtained with the different
  variants.

Done, but could be done quite better with more time...
Postponed to a next article.


REVIEW 7

  I'm not sure I understood what is actually presented in Figure 4 and
  how it has been measured.

Clarified with a newer experiment.

  You state in the text that triSYCL cannot target GPUs yet, but Figure
  4 presents GPU results for triSYCL. Could you please clarify this.

The test case has been simplified.

  It would help if you could clarify how the version mentioned in the
  text (SYCL, SYCL with OpenCL, pure OpenCL) match to the legend used in
  Figure 4.

Solved.

  Why do the performance results differ when using pure OpenCL
  vs. triSYCL?  Shouldn't these basically execute the same computations
  and perform the same data transfers?

To be investigated in another article...
