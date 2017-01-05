# 3-DNS-Protocol

   There are several problems that arise in the standard
   Registrant/Registrar/Registry model when the operator of a zone is
   neither the Registrant nor the Registrar for the delegation.
   Historically the issues have been minor, and limited to difficulty
   guiding the Registrant through the initial changes to the NS records
   for the delegation.  As this is usually a one time activity when the
   operator first takes charge of the zone it has not been treated as a
   serious issue.

   When the domain on the other hand uses DNSSEC it necessary for the
   Registrant in this situation to make regular (sometimes annual)
   changes to the delegation in order to track KSK rollover, by updating
   the delegation's DS record(s).  Under the current model this is prone
   to Registrant error and significant delays.  Even when the Registrant
   has outsourced the operation of DNS to a third party the registrant
   still has to be in the loop to update the DS record.

   There is a need for a simple protocol that allows a third party DNS
   operator to update DS and NS records in a trusted manner for a
   delegation without involving the registrant for each operation.

   The protocol described in this draft is REST based, and when used
   through an authenticated channel can be used to establish the DNSSEC
   Initial Trust (to turn on DNSSEC or bootstrap DNSSEC).  Once DNSSEC
   trust is established this channel can be used to trigger maintenance
   of delegation records such as DS, NS, and glue records.  The protocol
   is kept as simple as possible. 

