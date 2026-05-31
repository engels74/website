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
<tr><td><div id="tag24211" onclick="CopyToClipboard('tag24211');return false;" class="tag-decoration">nightly</div><div id="tag10809" onclick="CopyToClipboard('tag10809');return false;" class="tag-decoration">nightly-bbe9bee</div><div id="tag22624" onclick="CopyToClipboard('tag22624');return false;" class="tag-decoration">nightly-cc61dc974b383e5bce04746274407448b6d0443e</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/bbe9beeea1a8b28bd80fd55590520175f213c462" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26710781459" target="_blank">2026-05-31 11:01:08</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag4099" onclick="CopyToClipboard('tag4099');return false;" class="tag-decoration">release</div><div id="tag23036" onclick="CopyToClipboard('tag23036');return false;" class="tag-decoration">release-bcf36ce</div><div id="tag10187" onclick="CopyToClipboard('tag10187');return false;" class="tag-decoration">release-5.0.3</div><div id="tag22793" onclick="CopyToClipboard('tag22793');return false;" class="tag-decoration">release-v5</div><div id="tag8350" onclick="CopyToClipboard('tag8350');return false;" class="tag-decoration">release-v5.0</div><div id="tag22684" onclick="CopyToClipboard('tag22684');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/bcf36cef7a746f9ef94e609755b9263b9a747688" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26710781564" target="_blank">2026-05-31 11:01:09</a></td></tr>
<tr><td><div id="tag14374" onclick="CopyToClipboard('tag14374');return false;" class="tag-decoration">testing</div><div id="tag31326" onclick="CopyToClipboard('tag31326');return false;" class="tag-decoration">testing-009193c</div><div id="tag10789" onclick="CopyToClipboard('tag10789');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag18931" onclick="CopyToClipboard('tag18931');return false;" class="tag-decoration">testing-v5</div><div id="tag18925" onclick="CopyToClipboard('tag18925');return false;" class="tag-decoration">testing-v5.0</div><div id="tag16" onclick="CopyToClipboard('tag16');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/009193c9e6c31de8f8cdff399b7f16aa7f6beaaf" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26710782493" target="_blank">2026-05-31 11:01:11</a></td></tr>
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
