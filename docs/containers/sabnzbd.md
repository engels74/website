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
<tr><td><div id="tag23673" onclick="CopyToClipboard('tag23673');return false;" class="tag-decoration">nightly</div><div id="tag8394" onclick="CopyToClipboard('tag8394');return false;" class="tag-decoration">nightly-ab11cb0</div><div id="tag6029" onclick="CopyToClipboard('tag6029');return false;" class="tag-decoration">nightly-920e23e11e51b0ff19de511cbba398b7d89d3b15</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/ab11cb04c3ff7345f187da9436b5d381752807a0" target="_blank">Version update: e898f92f49efc13c70479fe45cc402b7e46934eb => 920e23e11e51b0ff19de511cbba398b7d89d3b15</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21811979275" target="_blank">2026-02-09 04:06:17</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag355" onclick="CopyToClipboard('tag355');return false;" class="tag-decoration">release</div><div id="tag3717" onclick="CopyToClipboard('tag3717');return false;" class="tag-decoration">release-2bf7455</div><div id="tag8057" onclick="CopyToClipboard('tag8057');return false;" class="tag-decoration">release-4.5.5</div><div id="tag20273" onclick="CopyToClipboard('tag20273');return false;" class="tag-decoration">release-v4</div><div id="tag25965" onclick="CopyToClipboard('tag25965');return false;" class="tag-decoration">release-v4.5</div><div id="tag23935" onclick="CopyToClipboard('tag23935');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2bf7455ca506aeb132cea7493e58ea81d09b301f" target="_blank">Upstream update: alpinevpn-a8c5f31 => alpinevpn-6d5cbf5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21469645114" target="_blank">2026-01-29 07:35:38</a></td></tr>
<tr><td><div id="tag1230" onclick="CopyToClipboard('tag1230');return false;" class="tag-decoration">testing</div><div id="tag30765" onclick="CopyToClipboard('tag30765');return false;" class="tag-decoration">testing-045581e</div><div id="tag7977" onclick="CopyToClipboard('tag7977');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag6224" onclick="CopyToClipboard('tag6224');return false;" class="tag-decoration">testing-v4</div><div id="tag1289" onclick="CopyToClipboard('tag1289');return false;" class="tag-decoration">testing-v4.5</div><div id="tag24876" onclick="CopyToClipboard('tag24876');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/045581e27148697ee96df4505fa3abe854471819" target="_blank">Upstream update: alpinevpn-a8c5f31 => alpinevpn-6d5cbf5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21469645621" target="_blank">2026-01-29 07:35:39</a></td></tr>
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
