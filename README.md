# Deregistration-Procedure

When a device wants to access the services of 5G system. It has to register itself with the network. When it is no longer wants access the services, it has to deregistered from the 5G network. This is known as deregistration procedure.

The network can also initiate the deregistration procedure when it wants to kick out the device from the 5G network. Let us look on the registration procedure when the device is being turned off and it would like to deregister from the network.

**Deregistration-Procedure Call Flows**

In the first step, the device tries to forward the deregistration request to the AMF by the RAN and after receiving the deregistration request, the AMF has to tear down the any session related context. So first it contacts with the SMF to release any UE related context associated with the ongoing PDU session.

So the SMF receives the request and ask to the UPF to release any userplane resources associated with this PDU session. The SMF forward the conformation back to the AMF, saying that the user plane resources are now released which means UE-context is also released. 

Now based on this, the SMF also notifies the PCF that it no longer required any policies associations that are associated with this PDU session. And it also unsubscribe from the UDM that is no longer needs any update that ot was previously requested from UDM. 

And the SMF also deregistered from the UDM saying that, this PDU session is no longer valid. The SMF notifies the PCF that the policy association related to the access management are no longer necessary. Then the AMF notifies the PCF that any policies related to device specific management are also no longer needed.

Once the PDU session are turned down and all the policies have been disconnected. Then the AMF confirms to the device that deregistration is accepted. Now the AMF also notifies to release the radio access network connection information so that any wireless device context stored in the gNodeB can also be released.
