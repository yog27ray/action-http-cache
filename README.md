### This is extended work of https://github.com/kevincobain2000/action-cache-http
### Dependency cache installation for Github Enterprise - self hosted runners

https://medium.com/web-developer/github-actions-solving-actions-cache-v2-for-self-hosted-runners-on-github-enterprise-663f22caeee3
### Server Setup

https://github.com/kevincobain2000/cache-http
### Installation

```
    - name: Yarn Install (with cache)
      uses: yog27ray/action-cache-http@v1
      with:
        version: ${{ matrix.node-versions }}
        lock_file: yarn.lock
        install_command: yarn install
        destination_folder: node_modules
        // Speed up caching at the cost of more storage space
        disable_compression: true
        operating_dir: "./" # optional
        ignore_fields: "version,name" # optional
        cache_http_api: "https://yourdomain.com/path/to/installation/cache-http"
        http_proxy: ""
```
