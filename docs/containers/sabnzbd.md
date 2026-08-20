---
hide:
  - toc
title: engels74/sabnzbd
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/sabnzbd){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/sabnzbd){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Upstream Project](https://sabnzbd.org){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="/img/image-logos/sabnzbd.svg" alt="logo"></div>

!!! question "What is this?"

    This is a fork of Hotio's [SABnzbd](https://hotio.dev/containers/sabnzbd) Docker image, that includes ffprobe, at `/app/bin/ffprobe`. Useful for scripts.

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
<tr><td><div id="tag5070" onclick="CopyToClipboard('tag5070');return false;" class="tag-decoration">nightly</div><div id="tag2818" onclick="CopyToClipboard('tag2818');return false;" class="tag-decoration">nightly-5878bb3</div><div id="tag9995" onclick="CopyToClipboard('tag9995');return false;" class="tag-decoration">nightly-611dfa74d2ad85a3cfa451748f0b6702f7007fe1</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/5878bb31c3f4beff8699b6e885a0aa0831fcf351" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32381394212" target="_blank">2026-08-20 14:38:53</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag6786" onclick="CopyToClipboard('tag6786');return false;" class="tag-decoration">release</div><div id="tag28534" onclick="CopyToClipboard('tag28534');return false;" class="tag-decoration">release-87f6728</div><div id="tag31693" onclick="CopyToClipboard('tag31693');return false;" class="tag-decoration">release-5.1.1</div><div id="tag27361" onclick="CopyToClipboard('tag27361');return false;" class="tag-decoration">release-v5</div><div id="tag25445" onclick="CopyToClipboard('tag25445');return false;" class="tag-decoration">release-v5.1</div><div id="tag13099" onclick="CopyToClipboard('tag13099');return false;" class="tag-decoration">release-v5.1.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/87f6728be54de4685822ca23f362b10fc05add0c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32381402735" target="_blank">2026-08-20 14:38:57</a></td></tr>
<tr><td><div id="tag29839" onclick="CopyToClipboard('tag29839');return false;" class="tag-decoration">testing</div><div id="tag3242" onclick="CopyToClipboard('tag3242');return false;" class="tag-decoration">testing-e417274</div><div id="tag19619" onclick="CopyToClipboard('tag19619');return false;" class="tag-decoration">testing-5.1.1</div><div id="tag24227" onclick="CopyToClipboard('tag24227');return false;" class="tag-decoration">testing-v5</div><div id="tag25267" onclick="CopyToClipboard('tag25267');return false;" class="tag-decoration">testing-v5.1</div><div id="tag31025" onclick="CopyToClipboard('tag31025');return false;" class="tag-decoration">testing-v5.1.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/e417274da1817bfeeeadbb99d597f90b9d06a636" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32381393649" target="_blank">2026-08-20 14:38:53</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name sabnzbd \
        -p 8080:8080 \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e WEBUI_PORTS="8080/tcp,8080/udp" \
        -e ARGS="" \
        -e TZ="Etc/UTC" \
        -v /<host_folder_config>:/config \
        -v /<host_folder_data>:/data \
        ghcr.io/engels74/sabnzbd
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      sabnzbd:
        container_name: sabnzbd
        image: ghcr.io/engels74/sabnzbd
        ports:
          - "8080:8080"
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
          - WEBUI_PORTS=8080/tcp,8080/udp
          - ARGS
        volumes:
          - /<host_folder_config>:/config
          - /<host_folder_data>:/data
    ```

--8<-- "includes/wireguard.md"
