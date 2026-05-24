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
<tr><td><div id="tag2134" onclick="CopyToClipboard('tag2134');return false;" class="tag-decoration">nightly</div><div id="tag15782" onclick="CopyToClipboard('tag15782');return false;" class="tag-decoration">nightly-1fa0ffa</div><div id="tag6703" onclick="CopyToClipboard('tag6703');return false;" class="tag-decoration">nightly-25d20f0f08ce2078402faf0e7b281db9ceb04643</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/1fa0ffa9d6e2bf0e9e7c60f85a69eebc1b6d2ad5" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26352501761" target="_blank">2026-05-24 05:03:34</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag18811" onclick="CopyToClipboard('tag18811');return false;" class="tag-decoration">release</div><div id="tag20073" onclick="CopyToClipboard('tag20073');return false;" class="tag-decoration">release-5d3bf06</div><div id="tag8838" onclick="CopyToClipboard('tag8838');return false;" class="tag-decoration">release-5.0.3</div><div id="tag19170" onclick="CopyToClipboard('tag19170');return false;" class="tag-decoration">release-v5</div><div id="tag24962" onclick="CopyToClipboard('tag24962');return false;" class="tag-decoration">release-v5.0</div><div id="tag4814" onclick="CopyToClipboard('tag4814');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5d3bf06899838b31cb644df9e73542d3832ea42f" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26352501785" target="_blank">2026-05-24 05:03:34</a></td></tr>
<tr><td><div id="tag2683" onclick="CopyToClipboard('tag2683');return false;" class="tag-decoration">testing</div><div id="tag19968" onclick="CopyToClipboard('tag19968');return false;" class="tag-decoration">testing-aa16204</div><div id="tag3959" onclick="CopyToClipboard('tag3959');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag28395" onclick="CopyToClipboard('tag28395');return false;" class="tag-decoration">testing-v5</div><div id="tag10330" onclick="CopyToClipboard('tag10330');return false;" class="tag-decoration">testing-v5.0</div><div id="tag2042" onclick="CopyToClipboard('tag2042');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/aa16204d41da4854c3414a4c58e6c8e59abd15a0" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26343379597" target="_blank">2026-05-23 20:57:35</a></td></tr>
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
