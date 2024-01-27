# netbox-ansible-webinar

## Getting Started With The Ansible Playbooks

1. Clone the Git repo and change into the `netbox-ansible-webinar` directory:
    ```
    git clone https://github.com/netboxlabs/netbox-ansible-webinar.git
    cd netbox-ansible-webinar
    ```
2. Create and activate Python 3 virtual environment:
    ```
    python3 -m venv ./venv
    source venv/bin/activate
    ```
3. Upgrade pip:
    ```
    python3 -m pip install --upgrade pip
    ```
4. Install required Python packages:

    **option 1** - Install individual packages: 
    ```
    pip install pynetbox
    pip install ansible
    pip install pytz
    pip install ansible-pylibssh
    ```
    **option 2** - Install from 'requirements.txt' file: 
    ```
    pip install -r requirements.txt
    ```
5. Install
    ```
    ansible-galaxy collection install netbox.netbox
    ```
6. Set environment variables for the NetBox API token and URL:
    ```
    export NETBOX_API=<YOUR_NETBOX_URL> (note - must include http:// or https://) 
    export NETBOX_TOKEN=<YOUR_NETBOX_API_TOKEN>
    ```
7. List the devices and host variables retrieved from NetBox using the dynamic inventory: 
    ```
    ansible-inventory -i netbox_inv.yml --list
    ```
7. Run a playbook, for example: 
    ```
    ansible-playbook get_facts.yml
    ```
8. When you have finished working you can deactivate the Python virtual environment:
    ```
    deactivate
    ```

## TODO - Building the Virtual Network With Containerlab

1. Install Containerlab following these [instructions](https://containerlab.dev/install/)
2. Use the [Topology file](./containerlab/testlab.clab.yaml) 