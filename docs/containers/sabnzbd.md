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
<tr><td><div id="tag1134" onclick="CopyToClipboard('tag1134');return false;" class="tag-decoration">nightly</div><div id="tag9658" onclick="CopyToClipboard('tag9658');return false;" class="tag-decoration">nightly-9ad43e2</div><div id="tag19090" onclick="CopyToClipboard('tag19090');return false;" class="tag-decoration">nightly-7daa0159ec76fdee6bcfa81620a4300aee924d40</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/9ad43e2a2f1a279389969a5148f60a01ae8e7817" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27873973281" target="_blank">2026-06-20 14:25:36</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag8734" onclick="CopyToClipboard('tag8734');return false;" class="tag-decoration">release</div><div id="tag8715" onclick="CopyToClipboard('tag8715');return false;" class="tag-decoration">release-776e678</div><div id="tag22749" onclick="CopyToClipboard('tag22749');return false;" class="tag-decoration">release-5.0.4</div><div id="tag17880" onclick="CopyToClipboard('tag17880');return false;" class="tag-decoration">release-v5</div><div id="tag27668" onclick="CopyToClipboard('tag27668');return false;" class="tag-decoration">release-v5.0</div><div id="tag15557" onclick="CopyToClipboard('tag15557');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/776e678fe2d168b2e311463b46288f7b57d2e26f" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27873973790" target="_blank">2026-06-20 14:25:37</a></td></tr>
<tr><td><div id="tag2383" onclick="CopyToClipboard('tag2383');return false;" class="tag-decoration">testing</div><div id="tag14587" onclick="CopyToClipboard('tag14587');return false;" class="tag-decoration">testing-5996b41</div><div id="tag32713" onclick="CopyToClipboard('tag32713');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag11660" onclick="CopyToClipboard('tag11660');return false;" class="tag-decoration">testing-v5</div><div id="tag26217" onclick="CopyToClipboard('tag26217');return false;" class="tag-decoration">testing-v5.0</div><div id="tag8056" onclick="CopyToClipboard('tag8056');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5996b411ad9a9b78f21bf3d1ff849271e6578a00" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27873975239" target="_blank">2026-06-20 14:25:41</a></td></tr>
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
