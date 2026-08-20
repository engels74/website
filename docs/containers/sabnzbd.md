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
<tr><td><div id="tag22691" onclick="CopyToClipboard('tag22691');return false;" class="tag-decoration">nightly</div><div id="tag28463" onclick="CopyToClipboard('tag28463');return false;" class="tag-decoration">nightly-7be3a55</div><div id="tag18602" onclick="CopyToClipboard('tag18602');return false;" class="tag-decoration">nightly-602464349f88fc9ffd45b7f0b4c16ec48cb855c1</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/7be3a55367be39a4f7a40511a942694da61a5bad" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32393117748" target="_blank">2026-08-20 16:38:16</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag29100" onclick="CopyToClipboard('tag29100');return false;" class="tag-decoration">release</div><div id="tag20020" onclick="CopyToClipboard('tag20020');return false;" class="tag-decoration">release-87f6728</div><div id="tag4253" onclick="CopyToClipboard('tag4253');return false;" class="tag-decoration">release-5.1.1</div><div id="tag18390" onclick="CopyToClipboard('tag18390');return false;" class="tag-decoration">release-v5</div><div id="tag9582" onclick="CopyToClipboard('tag9582');return false;" class="tag-decoration">release-v5.1</div><div id="tag24254" onclick="CopyToClipboard('tag24254');return false;" class="tag-decoration">release-v5.1.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/87f6728be54de4685822ca23f362b10fc05add0c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32381402735" target="_blank">2026-08-20 14:38:57</a></td></tr>
<tr><td><div id="tag31779" onclick="CopyToClipboard('tag31779');return false;" class="tag-decoration">testing</div><div id="tag5819" onclick="CopyToClipboard('tag5819');return false;" class="tag-decoration">testing-e417274</div><div id="tag9064" onclick="CopyToClipboard('tag9064');return false;" class="tag-decoration">testing-5.1.1</div><div id="tag22788" onclick="CopyToClipboard('tag22788');return false;" class="tag-decoration">testing-v5</div><div id="tag5492" onclick="CopyToClipboard('tag5492');return false;" class="tag-decoration">testing-v5.1</div><div id="tag29981" onclick="CopyToClipboard('tag29981');return false;" class="tag-decoration">testing-v5.1.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/e417274da1817bfeeeadbb99d597f90b9d06a636" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32381393649" target="_blank">2026-08-20 14:38:53</a></td></tr>
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
