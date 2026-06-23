# best practices for dockerfiles

pin specific versiosn for security and build speed

this means base images, system dependencies, application dependencies

use small + secure base images for security and build speed

Protect the layer cache for build speed and clarity

order commands by frequency of change

copy dependency requirement file-> install deps-> copy remaining source code

use cache mounts

use COPY --link

combine steps that are always linked


Be explicit
set working dir with WORKDIR    
set indicated port with EXPOSE
set default environment variables with ENV

avoid unnecesary files
use dockerignore

COPY specific files

use non root user

Install only production dependencies

avoid sensitive info

leverage multi-step builds

for a base image consider, size, language support, ergonomics(package manage, utilities) and security