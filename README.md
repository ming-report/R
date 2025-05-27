Here’s a step-by-step guide to manually install R on CentOS 8.2.

1. Install EPEL and Required Dependencies

    sudo dnf install epel-release
   
    sudo dnf install wget tar make gcc gcc-c++ libcurl-devel libxml2-devel openssl-devel

2. Download and Install R from CRAN
   
    CentOS 8.2 repositories may not have the latest R.
    
    You can install R from source or use the EPEL repo (for a stable version).
    
    Option A: Install from EPEL (Recommended for Simplicity)
    
          sudo dnf install R
    
    Option B: Install Latest R from Source
    
      Download the latest R source:
      
          cd /tmp
          
          wget https://cran.r-project.org/src/base/R-4/R-4.3.3.tar.gz
          
          tar -xzvf R-4.3.3.tar.gz
          
          cd R-4.3.3
          
          Configure, build, and install:
          
          ./configure --enable-R-shlib
          
          make
          
          sudo make install

3. Verify Installation

       R --version

    You should see the installed R version.

4. (Optional) Install R Packages
   
  Start R and install packages as needed:

      R
      
      Inside R console:
      
      install.packages("ggplot2")
      
      q()


To manually install epel-release on CentOS 8.2, follow these steps:

1. Download the EPEL Release RPM

   sudo dnf install -y wget
   
   wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm

2. Install the EPEL Release RPM

   sudo dnf install -y epel-release-latest-8.noarch.rpm

3. Enable the EPEL Repository

   This is usually enabled automatically, but you can ensure it with:

       sudo dnf config-manager --set-enabled epel

4. Verify EPEL is Enabled

       dnf repolist

   You should see epel in the list.
