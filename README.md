# Example of using Jetstream to build a Docker container for Tesseract4 and convert it to a Singularity container

This instructions assum you already have access to an XSEDE allocation
on Jetstream and have experience launching a Virtual Machine (VM)
instance.

To get Docker and Singularity installed on the VM you can follow the
instructions to run the jetstream-setup script:

https://github.com/aculich/jetstream-setup

Now you're ready to build a Tesseract container on Jetstream, push it
to Dockerhub, and convert it to run as a Singularity container on
Jetstream, Savio, or anyehwere else that you have the Singularity
container runtime installed.
