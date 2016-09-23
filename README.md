# GSE
DVB Generic Stream Encapsulation implementation for amateur radio deployment. 

The two documents most useful for completing this code are:
Digital Video Broadcasting (DVB); Generic Stream Encapsulation (GSE) Protocol
Digital Video Broadcasting (DVB); Generic Stream Encapsulation (GSE) implementation guidelines

And anything else that helps, of course.

The pdf GSE_block_diagram in this repository is pages 19-22 of the GSE Implementation Guidelines. 
The classes in this GSE packet creation Python script are modeled after the blocks in the block diagram. 

The idea here is to write an implementation of GSE that will allow modeling and experimentation for Phase 4 Ground radios. 

We suspect that things like address fields and such may have to be "abused" a bit to get the right behaviors enabled. Testing these assumptions is important in order to get the radio design right.

Most of DVB assumes that you need to authorize a receiver as a legitimate subscriber. The receiver in amateur radio has different behavior. Authorization and authentication are functions in Phase 4, but the receiver must be able to monitor any traffic it wishes. Therefore, the address field may not necessarily contain the receiver's address, but may contain the transmitter's address. Things like that need to be fully tested. 

This implementation then becomes something to test the production implementation vectors against, to ensure that we are doing what we think we're doing. 
