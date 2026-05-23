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
<tr><td><div id="tag29113" onclick="CopyToClipboard('tag29113');return false;" class="tag-decoration">nightly</div><div id="tag26464" onclick="CopyToClipboard('tag26464');return false;" class="tag-decoration">nightly-3856d49</div><div id="tag17174" onclick="CopyToClipboard('tag17174');return false;" class="tag-decoration">nightly-fec57377dbc2a912a89ebdd33293723c55926411</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/3856d4952143a6a21c2a0037dec7beaf80b0d5e1" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26341271300" target="_blank">2026-05-23 19:16:24</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag32260" onclick="CopyToClipboard('tag32260');return false;" class="tag-decoration">release</div><div id="tag14187" onclick="CopyToClipboard('tag14187');return false;" class="tag-decoration">release-70d8e60</div><div id="tag28786" onclick="CopyToClipboard('tag28786');return false;" class="tag-decoration">release-5.0.3</div><div id="tag3124" onclick="CopyToClipboard('tag3124');return false;" class="tag-decoration">release-v5</div><div id="tag2933" onclick="CopyToClipboard('tag2933');return false;" class="tag-decoration">release-v5.0</div><div id="tag5427" onclick="CopyToClipboard('tag5427');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/70d8e606c26349a1a1d3680daa07fb14e8908e3a" target="_blank">Modified: meta.json, packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26287574256" target="_blank">2026-05-22 12:24:03</a></td></tr>
<tr><td><div id="tag22926" onclick="CopyToClipboard('tag22926');return false;" class="tag-decoration">testing</div><div id="tag8258" onclick="CopyToClipboard('tag8258');return false;" class="tag-decoration">testing-aa16204</div><div id="tag1255" onclick="CopyToClipboard('tag1255');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag2056" onclick="CopyToClipboard('tag2056');return false;" class="tag-decoration">testing-v5</div><div id="tag8549" onclick="CopyToClipboard('tag8549');return false;" class="tag-decoration">testing-v5.0</div><div id="tag22669" onclick="CopyToClipboard('tag22669');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/aa16204d41da4854c3414a4c58e6c8e59abd15a0" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26343379597" target="_blank">2026-05-23 20:57:35</a></td></tr>
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
