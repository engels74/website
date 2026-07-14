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
<tr><td><div id="tag16323" onclick="CopyToClipboard('tag16323');return false;" class="tag-decoration">nightly</div><div id="tag15446" onclick="CopyToClipboard('tag15446');return false;" class="tag-decoration">nightly-5eb169d</div><div id="tag15206" onclick="CopyToClipboard('tag15206');return false;" class="tag-decoration">nightly-ef2ee17c135c313e12c74455a0472edbae711e79</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/5eb169dd19414db47ce2583b4922b1bd1187fafc" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29317186854" target="_blank">2026-07-14 08:12:12</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag17902" onclick="CopyToClipboard('tag17902');return false;" class="tag-decoration">release</div><div id="tag10311" onclick="CopyToClipboard('tag10311');return false;" class="tag-decoration">release-5cab8a0</div><div id="tag3757" onclick="CopyToClipboard('tag3757');return false;" class="tag-decoration">release-5.0.4</div><div id="tag32320" onclick="CopyToClipboard('tag32320');return false;" class="tag-decoration">release-v5</div><div id="tag4362" onclick="CopyToClipboard('tag4362');return false;" class="tag-decoration">release-v5.0</div><div id="tag32736" onclick="CopyToClipboard('tag32736');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5cab8a094ea2eda370354e3287e77da5efab3700" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29317186467" target="_blank">2026-07-14 08:12:12</a></td></tr>
<tr><td><div id="tag9498" onclick="CopyToClipboard('tag9498');return false;" class="tag-decoration">testing</div><div id="tag13603" onclick="CopyToClipboard('tag13603');return false;" class="tag-decoration">testing-8a80aca</div><div id="tag28830" onclick="CopyToClipboard('tag28830');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag28732" onclick="CopyToClipboard('tag28732');return false;" class="tag-decoration">testing-v5</div><div id="tag29841" onclick="CopyToClipboard('tag29841');return false;" class="tag-decoration">testing-v5.0</div><div id="tag19625" onclick="CopyToClipboard('tag19625');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8a80aca145642c4e9646450e02336a81a7c1684e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29317185232" target="_blank">2026-07-14 08:12:10</a></td></tr>
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
