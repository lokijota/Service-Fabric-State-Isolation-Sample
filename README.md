# Azure Service Fabric State Isolation (mini) Sample
State Isolation in Azure Service Fabric sample

This is a *very simple* sample to demonstrate that state is isolated between reliable services in Azure Service Fabric, even if in the same application.

The solution contains a Service Fabric application (ServiceFabricDataIsolationSample) with two Stateful Services (StatefulService1 and StatefulService2). These were created with the default Stateful Service template in Visual Studio (the counter), and the only changes were:

- the trace to diagonistics has a prefix to say which of the services is writting it
- in StatefulService1 the initial value of the Counter is set at 1000

To test it, just publish to the local cluster (1 or 5 node), and open the Diagnostics window in Visual Studio (View > Other Windows > Diagnostic Events).

Note that this information is present in the documentation, but wanted to make sure. See "[...] The key difference between Reliable Collections and other high-availability technologies (such as Redis, Azure Table service, and Azure Queue service) is that *the state is kept locally in the service instance* while also being made highly available. [...]" in https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-reliable-services-reliable-collections .
