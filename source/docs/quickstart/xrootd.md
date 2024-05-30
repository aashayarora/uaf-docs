# Accessing UCSD's T2 XRootD Cluster

## Requesting Access

To request access to UCSD's T2 XRootD cluster for reading and writing files, follow these steps:

1. **Eligibility**: Ensure you are a part of a research group that collaborates with UCSD or has an official agreement for resource sharing.
2. **Access**: Please email t2support@physics.ucsd.edu stating that you need access to the cluster.

## Reading Files over XRootD

### Using `xrdcp`

The `xrdcp` command allows you to copy files from the XRootD cluster to your local machine or another remote location.

- **Syntax**: `xrdcp [options] source destination`
- **Example**: To copy a file from the cluster to your local machine:
  ```sh
  xrdcp root://redirector.t2.ucsd.edu:1095//path/to/remote/file /path/to/local/destination
  ```
- **Options**: Use `-f` for force overwrite and `-P` for parallel copying to improve transfer speed.

### Using `gfal-copy`

The `gfal-copy` command is another tool for file transfers, particularly useful for grid environments.

- **Syntax**: `gfal-copy [options] source destination`
- **Example**: To copy a file from the cluster to your local machine:
  ```sh
  gfal-copy davs://redirector.t2.ucsd.edu:1095//path/to/remote/file file:///path/to/local/destination
  ```
- **Options**: Use `-f` to force overwrite and `-v` for verbose output to get detailed transfer information.

## Reading Files from Inside ROOT

ROOT is a data analysis framework widely used in high energy physics. You can read files from the XRootD cluster directly within a ROOT session.

- **Example**: To open a file from the cluster:
  ```cpp
  TFile *file = TFile::Open("root://redirector.t2.ucsd.edu:1095//path/to/remote/file");
  // Proceed with your analysis
  ```
- Ensure you have the necessary ROOT version installed that supports XRootD.

## Additional Tips

- **Documentation**: Refer to the UCSD UAF documentation for detailed instructions and best practices.
- **Support**: If you encounter any issues, contact the support team at [t2support@physics.ucsd.edu](mailto:support@t2.ucsd.edu).