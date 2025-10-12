# How Profiling helps in Application Observability

Unlike traditional metrics which tells *what* happened, or logs/traces which show *when and where* something happened, profiling tells us *why* it happened by revealing exactly which parts of the code are consuming resources.

### How profiling helps in Observability

* **Root Cause at Code Level**
	* High latency is visible in traces, but reason behind the slowness is hidden.
	* Profiling can show if a method or library is consuming more CPU (for example, regex matching is using 60% of the CPU) or if a thread is locked waiting for I/O.
	* Connects application performance to actual code paths.
* **Continuous Performance Baseline**
	* Continuous profilers like Pyroscope or Parca  collect lightweight, always-on data
	* It can help tracking performance drifts over time.
* **Cost Optimisation**
	* Profiling shows inefficient loops or hot functions consuming compute.
	* Developers can fix or optimise these, leading to reduced resource consumption, helping in infrastructure savings.
* **Better Capacity Planning**
	* By analysing which code path dominates resource use, we can more accurately forecast infrastructure sizing.
* **Detecting Hidden Issues**
	* Unoptimised performance of the application can be invisible in logs/traces, but instantly show in a flamegraph.
