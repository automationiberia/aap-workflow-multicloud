# Create an Execution Environment

Here there's the basic configuration to create an Execution Environment:

```console
.
├── ansible.cfg                 (1)
├── bindep.txt                  (2)
├── build_ee.sh                 (3)
├── context                     (4)
│   ├── _build
│   │   ├── ansible.cfg
│   │   ├── bindep.txt
│   │   ├── requirements.txt
│   │   └── requirements.yml
│   └── Containerfile
├── execution-environment.yml   (5)
├── README.md                   (6)
├── requirements.txt            (7)
└── requirements.yml            (8)
```

> **NOTE**:
> 
> (1) Ansible configuration file to access the Galaxy (PAH) repositories.
>
> (2) Binary dependencies to add to the EE (usually installing RPM packages).
>
> (3) Script file to ease the execution.
>
> (4) Context directory with the Containerfile definition.
>
> (5) Execution Environment main definition file.
>
> (6) This README.md file.
>
> (7) Python requirements to be installed into the EE.
>
> (8) Ansible requirements to be installed into the EE (roles and collections).

The following command will create the EE called `sample` with the tag `latest` and will pull it to the `pah.example.com` PAH instance (that variable `AAH` is configured inside the script):

```bash
$ ./build_ee.sh sample:latest
```
