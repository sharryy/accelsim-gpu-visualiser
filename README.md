# Accel-Sim GPU Visualiser

An interactive, single-page visualisation of a multi-chiplet GPU as modelled by
[Accel-Sim](https://github.com/accel-sim/accel-sim-framework) / GPGPU-Sim.

I built this to understand the simulator while working with it: how its config
parameters fit together, the sequence a memory request follows, and how the
simulator steps through time. It helped me see everything that is otherwise
spread across config files, logs and C++ code.

## What it shows

- **Hardware layout:** chiplets, clusters and SMs, L2 slices, DRAM channels, and
  the intra- and inter-chiplet networks
- **Request sequence:** local vs. remote requests, L2 hits and misses, every hop
  animated and counted
- **Clock domains:** no global clock. Each step jumps to the earliest next tick
  among the core, network, L2 and DRAM clocks.
- **Config playground:** edit chiplets, clusters, memory channels, clocks and
  network sizes, and see which combinations are consistent and which would crash
  the simulator

## Usage

Open `index.html` in a browser. No build step or dependencies.

It is a teaching tool, not a performance model: latencies are simplified, so
always confirm against a real simulator run.
