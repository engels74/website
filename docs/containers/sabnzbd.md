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
<tr><td><div id="tag24010" onclick="CopyToClipboard('tag24010');return false;" class="tag-decoration">nightly</div><div id="tag22879" onclick="CopyToClipboard('tag22879');return false;" class="tag-decoration">nightly-59dd0ef</div><div id="tag873" onclick="CopyToClipboard('tag873');return false;" class="tag-decoration">nightly-f259e47110d4c510540ca50a26c67bf20b1b09c9</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/59dd0ef967e73839d5d3a9baea55d56a3e8df2e3" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25919010700" target="_blank">2026-05-15 12:57:01</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag18955" onclick="CopyToClipboard('tag18955');return false;" class="tag-decoration">release</div><div id="tag9350" onclick="CopyToClipboard('tag9350');return false;" class="tag-decoration">release-506f918</div><div id="tag31343" onclick="CopyToClipboard('tag31343');return false;" class="tag-decoration">release-5.0.2</div><div id="tag28221" onclick="CopyToClipboard('tag28221');return false;" class="tag-decoration">release-v5</div><div id="tag28843" onclick="CopyToClipboard('tag28843');return false;" class="tag-decoration">release-v5.0</div><div id="tag4968" onclick="CopyToClipboard('tag4968');return false;" class="tag-decoration">release-v5.0.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/506f918e29db918bf12ac2670a35a106be219351" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25919009383" target="_blank">2026-05-15 12:57:00</a></td></tr>
<tr><td><div id="tag24405" onclick="CopyToClipboard('tag24405');return false;" class="tag-decoration">testing</div><div id="tag2520" onclick="CopyToClipboard('tag2520');return false;" class="tag-decoration">testing-98c343d</div><div id="tag10956" onclick="CopyToClipboard('tag10956');return false;" class="tag-decoration">testing-5.0.2</div><div id="tag6506" onclick="CopyToClipboard('tag6506');return false;" class="tag-decoration">testing-v5</div><div id="tag1072" onclick="CopyToClipboard('tag1072');return false;" class="tag-decoration">testing-v5.0</div><div id="tag27430" onclick="CopyToClipboard('tag27430');return false;" class="tag-decoration">testing-v5.0.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/98c343dbbcccbb71c1ef4e7dbb5a2f88e64d1a42" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25919013766" target="_blank">2026-05-15 12:57:06</a></td></tr>
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
