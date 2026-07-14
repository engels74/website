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
<tr><td><div id="tag22102" onclick="CopyToClipboard('tag22102');return false;" class="tag-decoration">nightly</div><div id="tag6069" onclick="CopyToClipboard('tag6069');return false;" class="tag-decoration">nightly-5eb169d</div><div id="tag10266" onclick="CopyToClipboard('tag10266');return false;" class="tag-decoration">nightly-ef2ee17c135c313e12c74455a0472edbae711e79</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/5eb169dd19414db47ce2583b4922b1bd1187fafc" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29317186854" target="_blank">2026-07-14 08:12:12</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag11481" onclick="CopyToClipboard('tag11481');return false;" class="tag-decoration">release</div><div id="tag21587" onclick="CopyToClipboard('tag21587');return false;" class="tag-decoration">release-5cab8a0</div><div id="tag15810" onclick="CopyToClipboard('tag15810');return false;" class="tag-decoration">release-5.0.4</div><div id="tag14705" onclick="CopyToClipboard('tag14705');return false;" class="tag-decoration">release-v5</div><div id="tag6073" onclick="CopyToClipboard('tag6073');return false;" class="tag-decoration">release-v5.0</div><div id="tag20450" onclick="CopyToClipboard('tag20450');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5cab8a094ea2eda370354e3287e77da5efab3700" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29317186467" target="_blank">2026-07-14 08:12:12</a></td></tr>
<tr><td><div id="tag27086" onclick="CopyToClipboard('tag27086');return false;" class="tag-decoration">testing</div><div id="tag7615" onclick="CopyToClipboard('tag7615');return false;" class="tag-decoration">testing-432fb34</div><div id="tag10833" onclick="CopyToClipboard('tag10833');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag25126" onclick="CopyToClipboard('tag25126');return false;" class="tag-decoration">testing-v5</div><div id="tag25300" onclick="CopyToClipboard('tag25300');return false;" class="tag-decoration">testing-v5.0</div><div id="tag6390" onclick="CopyToClipboard('tag6390');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/432fb3421b5a0e248fe2d8f59656461649108a28" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29308897588" target="_blank">2026-07-14 05:34:37</a></td></tr>
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
