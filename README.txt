* Bring up EC2 (amzn Linux),
* Install Docker
* Replace the default lookback device storage driver (lookback devices)

How to run the playbook
-- set up aws credential with aws configure --profile <profile name>
-- export AWS_PROFILE=<profile name> for aws credential needed by ansibleplay
-- example:
export AWS_PROFILE=<profile name>
ansible-playbook launch-docker-host.yml --extra-vars='
vpc_id=vpc-1234abcd
vpc_subnet_id=subnet-cc33dd44
instance_type=t2.large'

Most of the parameters can be overwritten, usch as using --extra-var option

TODO:
 1. The inital ingress rule sholuld be for 'My IP Only'
 2. Using ansible to find the latest amzn linux AMI
 3. Has optiont of using other Linux flavors
 4. Follow ansible best practice to group/split the tasks with roles
 5. Find the way to monitor the storage usage
