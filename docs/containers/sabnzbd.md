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
<tr><td><div id="tag7616" onclick="CopyToClipboard('tag7616');return false;" class="tag-decoration">nightly</div><div id="tag232" onclick="CopyToClipboard('tag232');return false;" class="tag-decoration">nightly-92615b0</div><div id="tag14833" onclick="CopyToClipboard('tag14833');return false;" class="tag-decoration">nightly-5025f9ec5d8fb2aa41b277f299543e3f42b321b3</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/92615b00f57c10b151db7f99244a0ad028c82094" target="_blank">Version update: 5b3a8fcd3f8586c00c8d38b45f3d4d65d5bd122a => 5025f9ec5d8fb2aa41b277f299543e3f42b321b3</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21582624523" target="_blank">2026-02-02 08:24:50</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag9808" onclick="CopyToClipboard('tag9808');return false;" class="tag-decoration">release</div><div id="tag4305" onclick="CopyToClipboard('tag4305');return false;" class="tag-decoration">release-2bf7455</div><div id="tag1339" onclick="CopyToClipboard('tag1339');return false;" class="tag-decoration">release-4.5.5</div><div id="tag23486" onclick="CopyToClipboard('tag23486');return false;" class="tag-decoration">release-v4</div><div id="tag10396" onclick="CopyToClipboard('tag10396');return false;" class="tag-decoration">release-v4.5</div><div id="tag7948" onclick="CopyToClipboard('tag7948');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2bf7455ca506aeb132cea7493e58ea81d09b301f" target="_blank">Upstream update: alpinevpn-a8c5f31 => alpinevpn-6d5cbf5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21469645114" target="_blank">2026-01-29 07:35:38</a></td></tr>
<tr><td><div id="tag5996" onclick="CopyToClipboard('tag5996');return false;" class="tag-decoration">testing</div><div id="tag17691" onclick="CopyToClipboard('tag17691');return false;" class="tag-decoration">testing-045581e</div><div id="tag31350" onclick="CopyToClipboard('tag31350');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag7048" onclick="CopyToClipboard('tag7048');return false;" class="tag-decoration">testing-v4</div><div id="tag539" onclick="CopyToClipboard('tag539');return false;" class="tag-decoration">testing-v4.5</div><div id="tag21951" onclick="CopyToClipboard('tag21951');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/045581e27148697ee96df4505fa3abe854471819" target="_blank">Upstream update: alpinevpn-a8c5f31 => alpinevpn-6d5cbf5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21469645621" target="_blank">2026-01-29 07:35:39</a></td></tr>
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
