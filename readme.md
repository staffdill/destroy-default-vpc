#The goal of this module is to automate the deletion of the default vpcs within our amazon accounts for all regions they are created automatically and pose a security risk. 

#This script uses the aws CLI with the variables $aws_region, as well as $aws_profile to build a nested loop of all the default VPCs in the regions you supply it, and then takes apart the dependencies before finally deleting the VPC.

#The Script first identifies the VPCs in the account/regions based off the isDefault value being true, and will remove all components. There is a null resource module within this folder that calls the script and allows you to pass in as many regions as you would like.

#regions you want to deploy to are dicated in the deploy/variables/ var.aws_regions_cleanup list which you can add or remove from, these will create seperate null resources based off the each region.
