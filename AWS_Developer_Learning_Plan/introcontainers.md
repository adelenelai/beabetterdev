# Introduction to Containers
2 April 2024

* standardisation: size and dimensions consistent
* standardised unit of software to run on any computing environment
* form of virtualisation on OS level
* one server can host several containers e.g. multiple services or separate applications
* bare-metal servers > server hardware > OS > libraries > Applications A, B, C
  * Apps all  fight for same resources
  * Libraries must be in sync
* VMs > OS > Virtulisation Platform > VMs (each with their own libraries and OS)
  * but many OS running at same time - more updates, patching, more space taken up, more redundancy (possible same OS and same libraries)
* Containers > server hardware > OS > containerisation platform > shared libraries > Apps A, B, C
  * container images using file system layers
  * container runtime shares same OS kernel
  * spinup and down faster than VMs
  * can share libraries and isolate libraries as needed
* Docker (2013 release) popularised containers in recent years - portable, single immutable artifacts (images)
  * image = a read-only template for container
  * Dockerfile to create image - each instruction (line) in Dockerfile adds layer to image
  * changing docker file --> need to rebuild image --> only the changed layer is rebuilt! (awesome - small and fast)
  * each container is instance of an image
  * NOT a storage unit, but rather a discrete compute unit
* Microservice environments - containers suited to microservices
  * speeds up deployment cycles
  * monolithic traditional architectures - redundancies
  * each app is independent service, communicates via API, services can be updated, deployed, scaled easily
  * well-designed microservices: decentralised (each container uses its own language best suited to app)
    * smart endpoints and dumb pipes
    * waterfall vs. microservice (independent products, not projects)
    * designed for failure
    * disposability
    * dev and production parity --> DevOps

    
