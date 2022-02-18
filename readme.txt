#*************************************#
#                                     #
#    externaleutrancellfdd.mos        #
#              readme                 #
#                                     #
#*************************************#

Externaleutrancellfdd.mos adds all missing cells of all wanted neighbor nodes -as externaleutrancells and adds X2-interfaces too.
The script checks the existence of all relevant MOs and adds them on both sides if missed.
The only input needed is the list of the wanted X2-relation(s), like:

69012BB2-69014BB2
69011BB2-69014BB2
69010BB2-69011BB2

Prerequisites:
The script may be started from offline moshell on ENM, as it logins to each node automatically -using the "monode command".
Note that since the cmd "monode" is not supported by Amos, this script doesn't run on Amos either.
Ensure that ~/moshell/sitefiles/ipdatabase is up to date and includes the addresses of all the affected nodes.
Also, always ensure that variables are set correctly in your ~/.moshellrc so that login to nodes can work -based on nodenames only.

Usage:
After running the script (run externaleutrancellfdd_main.mos) it asks whether you have a file with the list of X2s.

	a) If the answer is yes, then the expected format is displayed.
	Then it asks the (path/filename)

	b) If the answer is no, then a manual input dialogue opens.
	The expected input format is: nodename (source-target) uppercase letters + numbers, separated by dash (e.g: 69012BB2-69014BB2).
	Having a list of nodes, you need to enter each relation line-by-line then hit "f" when finished.

The script works on Ipsec X2s (Direct IpSec via X2-feature).

Structure of the script:
externaleutrancellfdd_main.mos					#The main script to run
externaleutrancellfdd_sourcesub
externaleutrancellfdd_targetsub
externaleutrancellfdd_xtworesulttargetsub
externaleutrancellfdd_functions
externaleutrancellfdd_readme.txt

This script doesn't add eventual missing eutran frequencies, frequency relations and cell relations.
Separate scripts are available for that purpose (See: https://github.com/codgersanya/Relations).