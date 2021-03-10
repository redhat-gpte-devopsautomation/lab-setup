# lab-setup
ENV_TYPE can be any name you want to give according to the module.

## Provision Sub Lab Env
ansible-playbook main-playbook.yml -e env_type=${ENV_TYPE} -e guid=${GUID} -e email=${EMAIL}

### What will happen when env is provisioned?:
1. New OSP stack will be created according to the vars
2. `A` record for all the instances will be generated and updated to example.com.zone file
3. ALl the OSP instances will be registered to Satellite.

## Destroy
ansible-playbook subenv-delete.yml -e env_type=${ENV_TYPE} -e guid=${GUID} -e email=${EMAIL}

## Env Variable Files 
ls -l ~/lab-setup/vars/{tower,multi-dev}

You can create your own env var file setting up the labs for your module.

## Networks:
1. Default - Bastion Host and Satellite
2. Dev - Multi tier Env for 1st Module
3. Tower - Tower Nodes
4. Prod - Building Cloud and Tower Module

## Important:
1. DNS Container is pre configured
2. Satellite with Actication key is preconfigured



