build container image

docker push username/image_name:image_tag

docker tag my-scratch-image matthewbozoukov/my-scratch-image:abc123 (this is the tag)

if you push with no tag, defaults to the tag "latest"