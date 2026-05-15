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
<tr><td><div id="tag19585" onclick="CopyToClipboard('tag19585');return false;" class="tag-decoration">nightly</div><div id="tag21999" onclick="CopyToClipboard('tag21999');return false;" class="tag-decoration">nightly-a85e1ef</div><div id="tag27860" onclick="CopyToClipboard('tag27860');return false;" class="tag-decoration">nightly-60f555117c78466704bcb82b22cc5027944e8139</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/a85e1ef07ba67e9ae51541b177296714bbe794f4" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25923353620" target="_blank">2026-05-15 14:29:54</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag30698" onclick="CopyToClipboard('tag30698');return false;" class="tag-decoration">release</div><div id="tag8646" onclick="CopyToClipboard('tag8646');return false;" class="tag-decoration">release-506f918</div><div id="tag22199" onclick="CopyToClipboard('tag22199');return false;" class="tag-decoration">release-5.0.2</div><div id="tag27953" onclick="CopyToClipboard('tag27953');return false;" class="tag-decoration">release-v5</div><div id="tag19326" onclick="CopyToClipboard('tag19326');return false;" class="tag-decoration">release-v5.0</div><div id="tag14727" onclick="CopyToClipboard('tag14727');return false;" class="tag-decoration">release-v5.0.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/506f918e29db918bf12ac2670a35a106be219351" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25919009383" target="_blank">2026-05-15 12:57:00</a></td></tr>
<tr><td><div id="tag18931" onclick="CopyToClipboard('tag18931');return false;" class="tag-decoration">testing</div><div id="tag20369" onclick="CopyToClipboard('tag20369');return false;" class="tag-decoration">testing-98c343d</div><div id="tag13900" onclick="CopyToClipboard('tag13900');return false;" class="tag-decoration">testing-5.0.2</div><div id="tag8897" onclick="CopyToClipboard('tag8897');return false;" class="tag-decoration">testing-v5</div><div id="tag28951" onclick="CopyToClipboard('tag28951');return false;" class="tag-decoration">testing-v5.0</div><div id="tag19070" onclick="CopyToClipboard('tag19070');return false;" class="tag-decoration">testing-v5.0.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/98c343dbbcccbb71c1ef4e7dbb5a2f88e64d1a42" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25919013766" target="_blank">2026-05-15 12:57:06</a></td></tr>
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
