.. The contents of this file are included in multiple topics.
.. This file should not be changed in a way that hinders its ability to appear in multiple documentation sets.


A guard can be used to evaluate the state of a node during the execution phase of the |chef client| run. Based on the results of this evaluation, a guard is then used to tell the |chef client| if it should continue executing a resource. A guard accepts either a string value or a |ruby| block value:

* A string is executed as a shell command. If the command returns ``0``, the guard is applied. If the command returns any other value, then the guard is not applied.
* A block is executed as |ruby| code that must return either ``true`` or ``false``. If the block returns ``true``, the the guard is applied. If the block returns ``false``, the guard is not applied.

A guard is useful for ensuring that a resource is idempotent by allowing a resource to test for the desired state as it is being executed, and then if the desired state is present, for the |chef client| to do nothing.

