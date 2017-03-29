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

```bash
git clone https://github.com/aculich/tesseract-containerized
cd tesseract-containerized
docker build --rm --tag tesseract .
docker tag tesseract:latest aculich/tesseract:latest
docker push aculich/tesseract:latest
docker images
sudo singularity create --size 375 tesseract.img
sudo singularity import tesseract.img docker://aculich/tesseract:latest
singularity exec tesseract.img tesseract -v
```

[![asciicast](https://asciinema.org/a/42f9r49pqhcf42c8atb6eeat8.png)](https://asciinema.org/a/42f9r49pqhcf42c8atb6eeat8)
