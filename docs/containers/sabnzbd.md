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
<tr><td><div id="tag5851" onclick="CopyToClipboard('tag5851');return false;" class="tag-decoration">nightly</div><div id="tag31675" onclick="CopyToClipboard('tag31675');return false;" class="tag-decoration">nightly-a85e1ef</div><div id="tag25340" onclick="CopyToClipboard('tag25340');return false;" class="tag-decoration">nightly-60f555117c78466704bcb82b22cc5027944e8139</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/a85e1ef07ba67e9ae51541b177296714bbe794f4" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25923353620" target="_blank">2026-05-15 14:29:54</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag22651" onclick="CopyToClipboard('tag22651');return false;" class="tag-decoration">release</div><div id="tag26744" onclick="CopyToClipboard('tag26744');return false;" class="tag-decoration">release-cb443c6</div><div id="tag16743" onclick="CopyToClipboard('tag16743');return false;" class="tag-decoration">release-5.0.2</div><div id="tag28510" onclick="CopyToClipboard('tag28510');return false;" class="tag-decoration">release-v5</div><div id="tag16887" onclick="CopyToClipboard('tag16887');return false;" class="tag-decoration">release-v5.0</div><div id="tag3943" onclick="CopyToClipboard('tag3943');return false;" class="tag-decoration">release-v5.0.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/cb443c6f36468326b2b9d5456eba334f9c42d5c1" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25923352475" target="_blank">2026-05-15 14:29:53</a></td></tr>
<tr><td><div id="tag25495" onclick="CopyToClipboard('tag25495');return false;" class="tag-decoration">testing</div><div id="tag28165" onclick="CopyToClipboard('tag28165');return false;" class="tag-decoration">testing-98c343d</div><div id="tag22940" onclick="CopyToClipboard('tag22940');return false;" class="tag-decoration">testing-5.0.2</div><div id="tag20130" onclick="CopyToClipboard('tag20130');return false;" class="tag-decoration">testing-v5</div><div id="tag12880" onclick="CopyToClipboard('tag12880');return false;" class="tag-decoration">testing-v5.0</div><div id="tag17556" onclick="CopyToClipboard('tag17556');return false;" class="tag-decoration">testing-v5.0.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/98c343dbbcccbb71c1ef4e7dbb5a2f88e64d1a42" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25919013766" target="_blank">2026-05-15 12:57:06</a></td></tr>
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
