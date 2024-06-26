# Debugging at Scale – gdb4hpc, valgrind4hpc, ATP, stat

*Presenter: Thierry Braconnier (HPE)*

<!--
Course materials will be provided during and after the course.
-->

<!--
Temporary location of materials (for the lifetime of the training project):

-   Slides: `/project/project_465001098/Slides/HPE/07_debugging_at_scale.pdf`
-->

Archived materials on LUMI:

-   Slides: `/appl/local/training/4day-20240423/files/LUMI-4day-20240423-2_03_Debugging_at_Scale.pdf`

-   Recording: `/appl/local/training/4day-20240423/files/LUMI-4day-20240423-2_03_Debugging_at_Scale.pdf`

These materials can only be distributed to actual users of LUMI (active user account).

## Q&A

3.  Can all these tools be used with GPU offloading?

    -   Sanitizers are not available for the GPUs with rocm 5.2, 
        AMD is working on that with [ROCm 5.7](https://rocm.docs.amd.com/en/docs-5.7.0/understand/using_gpu_sanitizer.html).
