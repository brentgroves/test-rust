Notes: did not git push to work so had to push the image from docker push.
https://github.com/devcontainers/cli/tree/main/example-usage#building-an-image-from-devcontainerjson
Building an image from devcontainer.json
You can use the example by opening a terminal and typing the following:

image-build/build-image.sh
The resulting image name defaults to devcontainer-cli-test-image, but you can change it with the first argument, and configure it to push to a registry by setting the second argument to true. The third argument allows you to build for multiple architectures.
image-build/build-image.sh brentgroves/test-rust:1 true "linux/amd64"
image-build/build-image.sh ghcr.io/my-org/my-image-name-here true "linux/amd64 linux/arm64"
Ultimately, this script just calls the devcontainer build command to do all the work. Once built, you can refer to the specified image name directly in a devcontainer.json file using the image property.

image-build/build-image.sh brentgroves/test-rust:1 true "linux/amd64"
image-build/build-image.sh brentgroves/test-rust:1 true "linux/amd64"
devcontainer build --image-name brentgroves/test-rust:1 --push true --workspace-folder . 
devcontainer build --image-name $image_name --platform "$platforms" --push $push_flag --workspace-folder ..
