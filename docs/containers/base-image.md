---
hide:
  - toc
title: engels74/base-image
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/base-image){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/base-image){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Upstream Project](https://github.com/hotio/base){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="/img/image-logos/base-image.svg" alt="logo"></div>

!!! question "What is this?"

    This is a fork of Hotio's Docker image. It's used for my other Docker images. It's basically the same as Hotio's except that it's tailored to my containers.

<div id="tags-table">
  <table>
    <thead>
      <tr>
        <th>Tags <span class="twemoji" title="Click Tag to Copy"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M11 9h2V7h-2m1 13c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8m0-18A10 10 0 0 0 2 12a10 10 0 0 0 10 10 10 10 0 0 0 10-10A10 10 0 0 0 12 2m-1 15h2v-6h-2z"></path></svg></span></th>
        <th>Description</th>
        <th>Commit</th>
        <th>Last Updated</th>
      </tr>
    </thead>
    <tbody id="tags-table-body">
<tr><td><div id="tag8393" onclick="CopyToClipboard('tag8393');return false;" class="tag-decoration">alpinevpn</div><div id="tag16040" onclick="CopyToClipboard('tag16040');return false;" class="tag-decoration">alpinevpn-92f45b0</div></td><td>Alpine 3.23</td><td><a href="https://github.com/engels74/base-image/commit/92f45b040f08a7552ac6c79921ea8c10ea0befea" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/base-image/actions/runs/28588564271" target="_blank">2026-07-02 12:04:18</a></td></tr>
<tr><td><div id="tag15632" onclick="CopyToClipboard('tag15632');return false;" class="tag-decoration">noblevpn</div><div id="tag21819" onclick="CopyToClipboard('tag21819');return false;" class="tag-decoration">noblevpn-27a4ecc</div></td><td>Ubuntu 24.04</td><td><a href="https://github.com/engels74/base-image/commit/27a4ecc06d4742e3a467339f8e82341e9be1c8c8" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/base-image/actions/runs/28805962451" target="_blank">2026-07-06 16:13:36</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name base-image \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e TZ="Etc/UTC" \
        -v /<host_folder_config>:/config \
        ghcr.io/engels74/base-image:alpinevpn
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      base-image:
        container_name: base-image
        image: ghcr.io/engels74/base-image:alpinevpn
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
        volumes:
          - /<host_folder_config>:/config
    ```

This image is the base-image image for all other application images, however it can be used as a standalone VPN image for other images to attach to.

--8<-- "includes/wireguard.md"
