# Moving your AI training jobs to LUMI workshop - Copenhagen, May 29-30 2024

## Course organisation

-   Location: [NORDUNets, Kastruplundgade 22, DK-2770 Kastrup, Denmark](https://maps.app.goo.gl/nD6Q3ZRFU5st9Gk76)

-   [Schedule](schedule.md)

-   [HedgeDoc for questions](https://md.sigma2.no/lumi-ai-workshop-may24?both)
   
    Questions with longer-term relevance have been incorporated into the pages linked below.

<!-- 
-   There are two Slurm reservations for the course. One for each day:

    -   First day: `AI_workshop` (on the `small-g` Slurm partition)
    -   Second day: `AI_workshop_2` (on the `standard-g` Slurm partition)
-->


## Setting up for the exercises

### During the course

If you have an active project on LUMI, you should be able to make the exercises in that project.
To reduce the waiting time during the workshop, use the SLURM reservations we provide (see above).

You can find all exercises on our [AI workshop GitHub page](https://github.com/Lumi-supercomputer/Getting_Started_with_AI_workshop)


### After the termination of the course project

Setting up for the exercises is a bit more elaborate now.

-   The containers used in some of the exercises are no longer available in `/scratch/project_465001063/containers`.
    You'll have to replace that directory now with `/appl/local/training/software/ai-20240529`.

    Alternatively you can download the containers as 
    [a tar file](https://462000265.lumidata.eu/ai-20240529/files/ai-20240529-containers.tar)
    and untar in a directory of your choice (and point the scripts to that directory where needed).

-   The exercises as they were during the course are 
    [available as the tag `ai-202405291` in the GitHub repository](https://github.com/Lumi-supercomputer/Getting_Started_with_AI_workshop/tree/ai-202405291). Whereas the repository could simply 
    be cloned during the course, now you have to either:

    -   Download the content of the repository as 
        a [tar file](https://462000265.lumidata.eu/ai-20240529/files/ai-20240529-Getting_Started_with_AI_workshop.tar)
        or [bzip2-compressed tar file](https://462000265.lumidata.eu/ai-20240529/files/ai-20240529-Getting_Started_with_AI_workshop.tar.bz2)
        or [from the GitHub release](https://github.com/Lumi-supercomputer/Getting_Started_with_AI_workshop/releases/tag/ai-202405291)
        where you have a choice of formats,

    -   or clone the repository and then check out the tag `ai-202405291`:

        ```
        git clone https://github.com/Lumi-supercomputer/Getting_Started_with_AI_workshop.git
        cd Getting_Started_with_AI_workshop
        git checkout ai-202405291
        ```

Note also that any reference to a reservation in Slurm has to be removed.

The exercises were thoroughly tested at the time of the course. LUMI is an evolving supercomputer though,
so it is expected that some exercises may fail over time, and modules that need to be loaded, will also
change as at every update we have to drop some versions of the `LUMI` module as the programming environment
is no longer functional. Likewise it is expected that at some point the ROCm driver on the system may
become incompatible with the ROCm versions used in the containers for the course.


## Course materials

**Note:** Some links in the table below will remain invalid until after the course when all
materials are uploaded.

| Presentation | Slides | recording |
|:-------------|:-------|:----------|
| [Welcome and course introduction](extra_00_Course_Introduction.md) | / | [video](extra_00_Course_Introduction.md) |
| [Introduction to LUMI](extra_01_Introduction.md) | [slides](https://462000265.lumidata.eu/ai-20240529/files/LUMI-ai-20240529-01-Lumi_intro.pdf) | [video](extra_01_Introduction.md) |
| [Using the LUMI web-interface](extra_02_Webinterface.md) | [slides](https://462000265.lumidata.eu/ai-20240529/files/LUMI-ai-20240529-02-Using_LUMI_web_UI.pdf) | [video](extra_02_Webinterface.md) |
| [Hands-on: Run a simple PyTorch example notebook](E02_Webinterface.md) | / | [video](E02_Webinterface.md) |
| [Your first AI training job on LUMI](extra_03_FirstJob.md) | [slides](https://462000265.lumidata.eu/ai-20240529/files/LUMI-ai-20240529-03-First_AI_job.pdf) | [video](extra_03_FirstJob.md) |
| [Hands-on: Run a simple single-GPU PyTorch AI training job](E03_FirstJob.md) | / | [video](E03_FirstJob.md) |
| [Understanding GPU activity & checking jobs](extra_04_Workarounds.md) | [slides](https://462000265.lumidata.eu/ai-20240529/files/LUMI-ai-20240529-04-Understanding_GPU_activity.pdf) | [video](extra_04_Workarounds.md) |
| [Hands-on: Checking GPU usage interactively using rocm-smi](E04_Workarounds.md) | / | [video](E04_Workarounds.md) |
| [Running containers on LUMI](extra_05_RunningContainers.md) | [slides](https://462000265.lumidata.eu/ai-20240529/files/LUMI-ai-20240529-05-Running_containers_on_LUMI.pdf) | [video](extra_05_RunningContainers.md) |
| [Hands-on: Pull and run a container](E05_RunningContainers.md) | / | [video](E05_RunningContainers.md) |
| [Building containers from Conda/pip environments](extra_06_BuildingContainers.md) | [slides](https://462000265.lumidata.eu/ai-20240529/files/LUMI-ai-20240529-06-Building_containers_from_conda_pip_environments.pdf) | [video](extra_06_BuildingContainers.md) |
| [Hands-on: Creating a conda environment file and building a container using cotainr](E06_BuildingContainers.md) | / | / |
| [Extending containers with virtual environments for faster testing](extra_07_VirtualEnvironments.md) | [slides](https://462000265.lumidata.eu/ai-20240529/files/LUMI-ai-20240529-07-Extending_containers.pdf) | [video](extra_07_VirtualEnvironments.md) |
| [Scaling AI training to multiple GPUs](extra_08_MultipleGPUs.md) | [slides](https://462000265.lumidata.eu/ai-20240529/files/LUMI-ai-20240529-08-Scaling_multiple_GPUs.pdf) | [video](extra_08_MultipleGPUs.md) |
| [Hands-on: Converting the PyTorch single GPU AI training job to use all GPUs in a single node via DDP](E08_MultipleGPUs.md) | / | [video](E08_MultipleGPUs.md) |
| [Hyper-parameter tuning using Ray](extra_09_Ray.md) | [slides](https://462000265.lumidata.eu/ai-20240529/files/LUMI-ai-20240529-09-Hyperparameter_tuning_ray.pdf) | [video](extra_09_Ray.md) |
| [Hands-on: Hyper-parameter tuning the PyTorch model using Ray](E09_Ray.md) | / | [video](E09_Ray.md) |
| [Extreme scale AI](extra_10_ExtremeScale.md) | [slides](https://462000265.lumidata.eu/ai-20240529/files/LUMI-ai-20240529-10-Extreme_scale_AI.pdf) | [video](extra_10_ExtremeScale.md) |
| [Demo/Hands-on: Using multiple nodes](E10_ExtremeScale.md) | / | [video](E10_ExtremeScale.md) |
| [Loading training data from Lustre and LUMI-O](extra_11_LUMIO.md) | [slides](https://462000265.lumidata.eu/ai-20240529/files/LUMI-ai-20240529-11-Training_Data_on_LUMI.pdf) | [video](extra_11_LUMIO.md) |
| [Coupling machine learning with HPC simulation](extra_12_Coupling.md) | [slides](https://462000265.lumidata.eu/ai-20240529/files/LUMI-ai-20240529-12-Coupling_Simulation_and_AI.pdf) | [video](extra_12_Coupling.md) |


## Web links

-   LUMI documentation

    -   [Main documentation](https://docs.lumi-supercomputer.eu/)

    -   [Shortcut to the LUMI Software Library](https://lumi-supercomputer.github.io/LUMI-EasyBuild-docs/)
