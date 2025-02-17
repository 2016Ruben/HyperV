# HyperV: High-Performance Virtualization of the Programmable Data Plane


## NOTICE

As the codebase of HyperV has changed a lot since ICCCN'17, the [test cases](/tests) are not modified accordingly. So we are not sure that the test cases can work. However, we provide a [runtime controller](https://github.com/HyperVDP/HyperV-Controller.git) which provisions a high-level abstraction of HyperV based on [P4Runtime](https://github.com/p4lang/PI). We will give a logn-term support to the runtime controller. Thus we recommand you to use the runtime controller to manage the hypervisor. If you have any question, please refer Cheng Zhang at [cheng-zhang13@mails.tsinghua.edu.cn](cheng-zhang13@mails.tsinghua.edu.cn), or Yu Zhou at [y-zhou16@mails.tsinghua.edu.cn](y-zhou16@mails.tsinghua.edu.cn). We are very glad to offer our help and will try our best to answer your questions.

## About HyperV

 HyperV is a high-performance hypervisor provisions non-exclusive data plane abstraction and uninterrupted reconfigurability for the programmable data plane.

 ## The project

### [src](/src)

The source code of HyperV.

### [tests](/tests)

The test cases for HyperV.

### [tools](/tools)

The scripts for creating the testing environment.

## This repository has been updated to provide a more stable framework of HyperVDP. There is also more clarification added

### Makefile

1. Fill in the path to the targets folder of Bmv2.

### [tools](/tools)

1. First compile the code from the main folder.
	`sudo make compile`

2. Then start the switch from the main folder.
	`sudo make run`

3. There are duplicate actions in the compiled JSON file in the /build folder. These need to be removed first. Look at the added reference file in the main folder.

3. After switch setup cd into the /tools folder. Setup the match action tables.
	`./setup`

4. To populate the match action table of the switch.
	`./populate /Relative_path_to_folder_of_the_desired_test_case`

5. To clean up.
	`./clean`

### Tests
In the test folder the following command files are updated:

hyperv/firewall is error free.

hyperv/l2_switch is error free.

The only error to resolve for hyperv/router:
	`RuntimeCmd: Error: Table table_std_meta_match_stage1 needs 5 key fields`

The only error to resolve for hyperv/router:
	`RuntimeCmd: Error: Table table_std_meta_match_stage4 needs 5 key fields`

Duplicate errors have also been removed from hyperv/router/conf.json


## Custom topology

There is a topology file provided that can be used as an example.




