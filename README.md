# molecule-issue-2771

Validating a method to overide handlers. 

From the ansible documentations : https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html#handlers-running-operations-on-change

it states : 

- Handler names and listen topics live in a global namespace.

and :

- Use unique handler names. If you trigger more than one handler with the same name, the first one(s) get overwritten. Only the last one defined will run.

SO this is a quick validation to demosntrate how this can be used in testing with molecule.

while inport_role and role (instead of tasks), work as eexpeted ( the overide handler is called). Fo rthe include_role - the original role is called.

# Used this to run:

docker run --rm -it -v "$(pwd)":/tmp/$(basename "${PWD}") -v /var/run/docker.sock:/var/run/docker.sock -w /tmp/$(basename "${PWD}") quay.io/ansible/molecule:3.0.6 /bin/sh