# Synopsys Virtualizer Learning Task Map

This is a dependency-ordered learning map for becoming highly competent with Synopsys Virtualizer.

It is not time-based. It is task-based.

The idea is simple:

- Finish each stage by producing evidence.
- Do not move to the next stage until the current stage feels operational.
- Revisit earlier stages when later stages expose gaps.

This map is designed around the documentation currently readable in this workspace.

## How to use this map

For every task:

- read the referenced manual sections
- perform the task in the tool if possible
- write down what you learned
- keep evidence such as screenshots, commands, configs, scripts, logs, or notes

Use this completion scale:

- `Seen`: you have read about it
- `Tried`: you have done it once
- `Owned`: you can explain it and repeat it without help

## Stage 0: Establish the vocabulary and tool boundaries

### Goal

Understand what Virtualizer is, what a VDK is, and where the major tool layers fit.

### Read

- `Virtualizer Studio - User Guide`
  - `1.1 About This Manual`
  - `1.4.1 Virtualizer Development Kit (VDK)`
  - `1.4.2 VDK Project`
  - `1.4.3 VDK Building Block`
  - `1.4.4 Fixed VDK`
  - `1.4.5 Extensible VDK`
  - `1.4.10 VP Config`
- `VDK Creator - User Guide`
  - `1.1 About This Manual`
  - `Chapter 1 VDK Creator Overview`
- `VP Explorer - User Guide`
  - `1.1 About This Manual`
  - `2.3 1.3 VP Explorer Use Cases`

### Tasks

- Write your own one-page description of these terms:
  - Virtualizer Studio
  - VDK Creator
  - VP Explorer
  - VDK
  - Fixed VDK
  - Extensible VDK
  - VP Config
- Draw a simple stack diagram showing:
  - design-time tools
  - runtime/debug tools
  - simulation scripting
  - debugger integrations
  - packaging/distribution

### Evidence of completion

- You can explain the difference between:
  - `VDK project` and `Fixed VDK`
  - `VDK Creator` and `VP Explorer`
  - `VP Config` and `simulation executable`

## Stage 1: Become fluent in the IDE shell

### Goal

Be comfortable inside Virtualizer Studio as a working environment.

### Read

- `Virtualizer Studio - User Guide`
  - `Chapter 2 Getting Started with Virtualizer Studio`
  - `2.2 Launching the Virtualizer Studio IDE`
  - `2.3 Selecting the Eclipse Workspace`
  - `2.4 Virtualizer Studio Welcome Screen`
  - `2.6 GUI Icons`
  - `2.7 Launching the Virtualizer Studio Shell Application`
  - `2.8 Command-Line Arguments`
  - `3.5 Console View`
  - `3.5.2 Available Consoles`

### Tasks

- Launch Virtualizer Studio.
- Create or choose a clean workspace.
- Identify these perspectives if available:
  - VDK Creation
  - VDK Debug
  - TLM Creation
- Locate these consoles:
  - Virtualizer Studio Console
  - VP Explorer Tcl Console
  - CDT Build Console
  - GDB Hardware Debugging
- Launch `vssh` once and understand how it differs from the GUI.

### Evidence of completion

- You can explain what each console is for.
- You can say when to use GUI versus `vssh`.

## Stage 2: Learn to run an existing VDK before trying to build one

### Goal

Understand the user/operator flow before the builder flow.

### Read

- `VDK Creator - User Guide`
  - `2.11 Runtime Configurations`
  - `2.15 Running VDKs`
  - `2.15.2 Launching a VDK`
  - `Chapter 3 Running Fixed VDKs`
- `Virtualizer Studio - User Guide`
  - `1.4.4 Fixed VDK`
  - `1.4.10 VP Config`
- `VP Explorer - User Guide`
  - `Chapter 1 Getting Started`
  - `2.1 Working with VP Configs`
  - `2.2 Starting Simulations`

### Tasks

- Open an existing VDK or Fixed VDK project.
- Identify:
  - the active VP Config
  - the simulation executable
  - the working directory
  - the runtime configuration files
- Launch the VDK from the IDE.
- Restart the VDK.
- Observe what changes when you switch VP Config.

### Evidence of completion

- You can launch the same VDK using two different VP Configs.
- You can explain what changed between those runs.

## Stage 3: Master VP Configs

### Goal

Gain operational control over how a virtual platform is run.

### Read

- `VP Explorer - User Guide`
  - `Chapter 2 Using VP Configs`
  - `2.3 What are VP Projects and VP Configs?`
  - `2.3.2 VP Project File`
  - `2.3.3 VP Config File`
  - `2.5 Editing VP Configs`
  - `2.5.2 Overview Tab`
  - `2.5.3 Parameters Tab`
  - `2.5.4 Images Tab`
  - `2.5.5 Analysis Tab`
  - `2.5.6 Debug Tab`
  - `2.5.7 Environment Tab`
  - `2.7 Using VP Configs from the VP Explorer Command Line`
  - `2.8 Using VP Configs using Tcl CLI`
  - `Chapter 3 Layering VP Configs`

### Tasks

- Open a VP Config and inspect every tab.
- Create your own copy of an existing VP Config.
- Change:
  - one parameter
  - one image path
  - one environment setting
  - one debug-related setting
- Learn when to create a new VP Config versus modifying an old one.
- Practice launching a simulation from:
  - the IDE
  - VP Explorer
  - command line if possible

### Evidence of completion

- You can explain the role of each VP Config tab.
- You can create a new VP Config from scratch or from a copy.

## Stage 4: Learn image loading, symbol loading, and `.elf` usage

### Goal

Understand how software enters the simulated target.

### Read

- `VP Explorer - User Guide`
  - `2.5.4 Images Tab`
  - `4.2.1.6 Loading Software Images to the Simulation`
  - `7.4.4 Creating Custom OS Kits`
  - `7.4.5 Adding Support for Custom Software Image Formats`
- `Virtualizer Studio - User Guide`
  - `1.4.10 VP Config`

### Tasks

- Find the software image settings in the VP Config `Images` tab.
- Understand the difference between:
  - image
  - symbols
  - image + symbols
  - A2L
  - program map only
- Load a binary through the VP Config.
- Load a binary through the Design Browser `Load Image` flow.
- Confirm whether the image contains symbols.
- If using ELF, verify that the ELF can carry both the image and symbols.

### Evidence of completion

- You can explain how the tool loads software into the simulation.
- You can explain the difference between loading an image and loading only symbols.

## Stage 5: Build your own `.elf` using the documented flow

### Goal

Execute the clearest documented embedded-software build flow in the docs.

### Read

- `VDK Creation Methodology - Manual`
  - `9.2.6 Cross-Platform Build and Debug Environment`
  - `9.2.7 Running and Debugging the Starting Point VDK with the PlatformTest Configuration`
  - `9.2.7.1 Rebuild the PlatformTest Software Using CDT Tools`
  - `9.2.7.2 Configure the Resulting Binary File`
  - `9.2.7.3 Configuring the PlatformTest Image in the Corresponding VP Config`
  - `9.2.7.4 Use Eclipse CDT to Attach GDB to the Running VDK`
- `Virtualizer Studio - User Guide`
  - `3.5.2 Available Consoles`

### Tasks

- Import the `PlatformTest` project into the workspace.
- Identify the embedded cross-development tools needed for your architecture.
- Rebuild `PlatformTest` with CDT.
- Find the generated `.elf`.
- Point the VDK's VP Config `initial_image` or equivalent image field to that local `.elf`.
- Launch the VDK with that VP Config.
- Attach GDB to the running simulation.

### Evidence of completion

- You have produced your own `.elf`.
- You have run that `.elf` in the VDK.
- You have attached a debugger to that run.

### Important note

This is the strongest explicitly documented `.elf` flow in the current manuals. It is centered on `PlatformTest` and integration testing.

## Stage 6: Learn embedded software debugging end to end

### Goal

Become comfortable debugging software running inside the virtual platform.

### Read

- `Embedded Software Debuggers - User Guide`
  - `1.3 Launch Debuggers from Virtualizer Studio`
  - `2.2 Automatically Launching GNU GDB in Virtualizer Studio`
  - `2.3 Manually Launching Embedded GNU GDB`
  - `2.4 Software and Simulation Run Controls in Eclipse Debug View`
  - `2.5 Multi Core Debugging`
  - `4.5.2 Loading Target Software and Symbols`
  - `6.2 Launching MDB`
  - `8.4 Connecting IAR Embedded Workbench`
  - `10.1 Launching a Simulation`
  - `12 Remote Debugging`
- `VP Explorer - User Guide`
  - `Chapter 4 Debugging`
  - `4.2.3 VP Disassembly View`
  - `4.4 Setting Breakpoints`

### Tasks

- Launch GDB automatically from Virtualizer Studio.
- Launch GDB manually once.
- Use breakpoints, stepping, registers, disassembly, and memory view.
- Understand how simulation run control differs from software run control.
- Try one alternate debugger flow on paper or in practice:
  - TRACE32
  - Arm DS
  - MDB
  - IAR
- Understand how symbol loading and image loading interact.

### Evidence of completion

- You can explain the difference between:
  - simulation control
  - software control
  - symbol loading
  - image download
- You can debug at least one multi-core or clustered case conceptually.

## Stage 7: Learn to inspect and analyze a running prototype

### Goal

Move from “can run it” to “can reason about it.”

### Read

- `VP Explorer - User Guide`
  - `4.2 Exploring the Virtual Prototype`
  - `4.2.1 Design Browser`
  - `4.2.2 Terminal View`
  - `4.2.3 VP Disassembly View`
  - `4.2.4 Data Watch View`
  - `4.2.5 Memory Map View`
  - `4.2.6 Memory View`
  - `4.2.7 Connectivity Browser`
  - `5.1 The Value of Analysis`
  - `5.2 Overview of Tracing and Analysis`
  - `5.3 Use Cases of Analysis`

### Tasks

- Use the Design Browser to locate key blocks.
- Open terminals and map them to UARTs or console devices.
- Follow executing software in disassembly.
- Inspect register and memory state.
- Inspect the memory map and connectivity.
- Enable one analysis configuration and review the result.

### Evidence of completion

- You can navigate from top-level VDK to a specific core, memory, or peripheral.
- You can identify where to inspect a symptom:
  - UART output
  - memory issue
  - instruction flow
  - connectivity issue

## Stage 8: Learn VDK design and assembly

### Goal

Understand how a VDK is constructed from reusable pieces.

### Read

- `VDK Creator - User Guide`
  - `2.2 VDK Projects and Files`
  - `2.3 Creating and Importing Projects`
  - `2.5 Project Configuration`
  - `2.6 Design Hierarchy`
  - `2.7 SpecFlow`
  - `2.8 Instance Configuration`
  - `2.9 Library Browser`
  - `2.10 Design Overview`
  - `2.12 Building VDK Designs`

### Tasks

- Open a VDK project and inspect the hierarchy.
- Add and remove a building block.
- Create a placeholder and resolve it.
- Rename and move instances.
- Read and edit SpecFlow tables.
- Inspect generation settings and build settings.
- Build the VDK and inspect the build output.

### Evidence of completion

- You can explain how building blocks, groups, placeholders, and SpecFlow work together.
- You can make a small structural change to a VDK and rebuild it.

## Stage 9: Learn Fixed VDK and packaging flows

### Goal

Understand how teams hand VDKs to downstream users.

### Read

- `Virtualizer Studio - User Guide`
  - `4 IP and VDK Packaging Flows`
  - `4.5 Virtualizer Development Kits`
  - `4.5.1 Fixed VDK Packaging`
  - `4.5.2 Extensible VDK Packaging`
  - `4.5.3 No VDK Packaging`
  - `4.6 Fixed VDKs`
  - `Chapter 5 Virtualizer Studio Build System Integration`
- `VDK Creator - User Guide`
  - `2.13 Packaging VDK Designs`
  - `2.14 Packaging VDK Building Blocks`
  - `Chapter 3 Running Fixed VDKs`

### Tasks

- Understand the difference between:
  - source VDK
  - extensible VDK
  - fixed VDK
  - no-VDK package
  - VP Config package
- Package a VDK mentally or practically.
- Track which artifacts are editable by runtime users and which are not.
- Learn what `vsmake` is for.

### Evidence of completion

- You can explain how a VDK is handed from platform developer to software user.
- You can explain where VP Configs fit in packaging and reuse.

## Stage 10: Learn the development methodology, not just the buttons

### Goal

Understand how Synopsys expects a professional VDK effort to be organized.

### Read

- `VDK Creation Methodology - Manual`
  - `Chapter 1 Introduction`
  - `1.6 The VDK Project Lifecycle`
  - `1.7 VDK Processes`
  - `Chapter 2 Project Management`
  - `Chapter 3 The Screening Phase`
  - `Chapter 4 The Planning Phase`
  - `Chapter 5 The Continuous Planning and Control Loop`
  - `Chapter 6 The Implementation Part`
  - `Chapter 8 Implementation - Prototype Creation with Virtualizer Studio`
  - `Chapter 9 Implementation - Virtual Prototype Testing with Virtualizer Studio`

### Tasks

- Write down the lifecycle of a VDK project in your own words.
- Identify the project artifacts you would expect on a professional VDK effort:
  - model list
  - feature list
  - requirements
  - test plan
  - release checklist
  - profiling
  - user documentation
- Understand where implementation, validation, packaging, and handoff occur.

### Evidence of completion

- You can explain how a professional VDK project differs from a one-off prototype.

## Stage 11: Learn model creation and the TLM side

### Goal

Move beyond using existing models into understanding how they are created and integrated.

### Read

- `VDK Creation Methodology - Manual`
  - `7 Implementation - Model Creation`
  - `7.2.1 Directory Structure of a TLM Creation Project in Virtualizer Studio`
  - `7.2.2 Virtualizer Studio Unit Test Framework for TLM Creation`
  - `7.2.4 Tool Operation for Test Driven Development`
  - `7.3 Process Details`
  - `7.4 Coding Best Practices`
  - `6.3.5 TLM Model Creation with Virtualizer Studio`
- `Virtualizer Studio Python Interface Reference Manual`
  - TLM Creator classes and build-related objects
- `TLM Creator Tcl Interface Reference Manual`
  - object model and global procedures

### Tasks

- Understand what a TLM project produces.
- Understand the unit test and test-driven-development expectations.
- Understand how model libraries are built and consumed by VDKs.
- Inspect the Python/Tcl object models enough to recognize the core abstractions.

### Evidence of completion

- You can describe how a TLM model becomes part of a VDK.

### Documentation gap

The readable workspace currently lacks a searchable `TLM Creator - User Guide`. That means this stage can be understood conceptually and through references, but not yet mastered from UI documentation alone.

## Stage 12: Learn simulation scripting and in-simulation automation

### Goal

Gain the ability to influence behavior from inside the simulation.

### Read

- `Simulation Scripting - User Guide`
  - `1.1 Concepts and Terminology`
  - `1.1.11 Comparison of Simulation Scripting and VDK Debug CLI`
  - `1.2 Use Cases for Simulation Scripting`
  - `2 Developing Simulation Scripts`
  - `3 Simulation Scripts Use Flows`
  - `4 Creating and Interacting with Python Threads`
  - `5 Python Simulation API`
  - `6 Simulation Probes Utilities`
- `Simulation Probes Python Interface Reference Manual`

### Tasks

- Understand when to use simulation scripting instead of VDK Debug CLI.
- Create or study:
  - a startup script
  - a thread script
  - a simple probe
  - a logging or tracing script
- Learn where scripts live:
  - inside VDK projects
  - inside script libraries
  - inside IP libraries

### Evidence of completion

- You can explain the difference between inside-the-simulation and outside-the-simulation automation.
- You can create or modify at least one simulation script feature.

## Stage 13: Learn profiling and performance engineering

### Goal

Go from functional understanding to performance understanding.

### Read

- `VP Profiling Guidelines`
  - `Chapter 2 Benchmarking`
  - `2.1 Measuring Simulation Performance`
  - `2.2 Defining a Solid Benchmark`
  - `Chapter 3 Top-Down VP Profiling`
  - `3.2 Using the Light-Weight Profiler`
  - `3.3 Finding Simulation Hotspots`
  - `Chapter 4 VP Profiling Techniques`
  - `4.3 SystemC Process Cost`
  - `4.4 SystemC Kernel Overhead`
  - `4.5 Dynamic Quantum Efficiency`
  - `Chapter 6 Top-Down Profiler`
  - `Chapter 7 Statistical Function Profiling`

### Tasks

- Learn the meaning of:
  - elapsed real time
  - real time factor
  - instruction throughput
  - quantum efficiency
- Run through the profiler views conceptually or practically.
- Practice turning a performance symptom into a profiling investigation.

### Evidence of completion

- You can explain how you would diagnose a slow simulation.

## Stage 14: Learn external debugger ecosystems

### Goal

Be able to support whichever debugger a team uses.

### Read

- `Embedded Software Debuggers - User Guide`
  - `Chapter 1 Supported Debuggers`
  - `Chapter 2 GNU GDB`
  - `Chapter 3 TRACE32`
  - `Chapter 4 Arm DS`
  - `Chapter 5 winIDEA`
  - `Chapter 6 MetaWare Debugger`
  - `Chapter 7 Green Hills MULTI`
  - `Chapter 8 IAR`
  - `Chapter 12 Remote Debugging`

### Tasks

- Pick one primary debugger and one backup debugger.
- Understand:
  - connection flow
  - symbol/image handling
  - multi-core support
  - restart behavior
  - remote debugging

### Evidence of completion

- You can explain how software teams connect their preferred debugger to a Virtualizer simulation.

## Stage 15: Learn co-simulation and mixed-domain integration

### Goal

Understand how Virtualizer participates in larger verification and mixed-language setups.

### Read

- `Co-Simulation with Third-Party HDL Simulators`
  - `2.1 Design Flow`
  - `2.2 Rules for SystemC-HDL Co-Simulation`
  - `2.3 Setting up the Environment for HDL Simulators`
  - `2.4 Mapping Ports`
  - `2.6 Creating an HDL Proxy Module Automatically`
  - `2.10 Creating SystemC Proxy Modules from SystemC Designs`
  - `2.13 Building and Running a Simulation`
  - `2.14 Debugging a SystemC-HDL Co-Simulation`

### Tasks

- Learn the co-simulation rules.
- Learn the role of:
  - top-level SystemC
  - proxy modules
  - port mapping
  - language switches
  - simulator environment setup

### Evidence of completion

- You can explain when co-simulation is needed and what constraints it imposes.

## Stage 16: Learn automation interfaces

### Goal

Be able to automate repetitive work and create reproducible flows.

### Read

- `Virtualizer Studio Python Interface Reference Manual`
- `VP Explorer Python Interface Reference Manual`
- `VP Explorer Tcl Interface Reference Manual`
- `TLM Creator Tcl Interface Reference Manual`

### Tasks

- Learn which automation interface fits which scope:
  - Studio-level automation
  - VP Explorer runtime automation
  - TLM creation object model
  - Tcl versus Python choices
- Script at least one repeatable flow:
  - create/open project
  - select compiler
  - build VDK
  - create VP Config
  - run simulation

### Evidence of completion

- You can automate a common workflow without using the GUI.

## Stage 17: Expert consolidation

### Goal

Combine all the pieces into an engineer-level capability.

### Capstone tasks

- Take an existing VDK and explain:
  - what it contains
  - how it is built
  - how it is run
  - how software is loaded
  - how it is debugged
  - how it would be packaged
- Build or rebuild a local `.elf`, run it in the VDK, and debug it.
- Modify a VDK configuration and explain the effect.
- Add or replace one building block in a design and rebuild.
- Use analysis or profiling to diagnose one functional or performance issue.
- Explain the difference between:
  - using a Fixed VDK
  - extending an Extensible VDK
  - building a VDK project locally
- Explain where simulation scripting fits relative to VP Explorer.
- Explain when you would need:
  - external debugger integration
  - co-simulation
  - model authoring
  - packaging
  - automation

### Evidence of completion

- You can teach the flow to another engineer.
- You can answer “where does this problem belong?” for most Virtualizer tasks.
- You can move comfortably between:
  - IDE
  - runtime/debug
  - software image flow
  - platform assembly
  - packaging
  - automation

## Practical end-state

If you complete this map properly, you should be able to say:

- I understand how Virtualizer Studio, VDK Creator, VP Explorer, simulation scripting, debuggers, and packaging fit together.
- I can run and debug VDKs, manage VP Configs, load software images, build the documented test `.elf` flow, and explain how VDKs are created and delivered.
- I know where the remaining gaps are, especially around deep TLM authoring if the TLM Creator UI guide is still not searchable.

## Known documentation gaps

- `TLM Creator - User Guide` is not currently available as a readable/searchable document in this workspace.
- `SystemC` foundational material is still not in a usable searchable form here.
- `MultiNode VDKs` is still not available as a readable/searchable replacement.

Those gaps do not block strong proficiency in the currently documented flows, but they do limit complete mastery of model-authoring internals and some advanced platform patterns.
