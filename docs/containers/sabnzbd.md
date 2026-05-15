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
<tr><td><div id="tag3552" onclick="CopyToClipboard('tag3552');return false;" class="tag-decoration">nightly</div><div id="tag32136" onclick="CopyToClipboard('tag32136');return false;" class="tag-decoration">nightly-60ed37d</div><div id="tag17787" onclick="CopyToClipboard('tag17787');return false;" class="tag-decoration">nightly-60f555117c78466704bcb82b22cc5027944e8139</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/60ed37d2e27aa0131f5d1cf796b81258a6135e21" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25925941112" target="_blank">2026-05-15 15:22:41</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag24794" onclick="CopyToClipboard('tag24794');return false;" class="tag-decoration">release</div><div id="tag14787" onclick="CopyToClipboard('tag14787');return false;" class="tag-decoration">release-cb443c6</div><div id="tag13088" onclick="CopyToClipboard('tag13088');return false;" class="tag-decoration">release-5.0.2</div><div id="tag4682" onclick="CopyToClipboard('tag4682');return false;" class="tag-decoration">release-v5</div><div id="tag31912" onclick="CopyToClipboard('tag31912');return false;" class="tag-decoration">release-v5.0</div><div id="tag1689" onclick="CopyToClipboard('tag1689');return false;" class="tag-decoration">release-v5.0.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/cb443c6f36468326b2b9d5456eba334f9c42d5c1" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25923352475" target="_blank">2026-05-15 14:29:53</a></td></tr>
<tr><td><div id="tag32153" onclick="CopyToClipboard('tag32153');return false;" class="tag-decoration">testing</div><div id="tag9655" onclick="CopyToClipboard('tag9655');return false;" class="tag-decoration">testing-322685a</div><div id="tag21611" onclick="CopyToClipboard('tag21611');return false;" class="tag-decoration">testing-5.0.2</div><div id="tag26245" onclick="CopyToClipboard('tag26245');return false;" class="tag-decoration">testing-v5</div><div id="tag9554" onclick="CopyToClipboard('tag9554');return false;" class="tag-decoration">testing-v5.0</div><div id="tag18521" onclick="CopyToClipboard('tag18521');return false;" class="tag-decoration">testing-v5.0.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/322685a21d1294a1431018b047ec3d171fdcafc0" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25923352904" target="_blank">2026-05-15 14:29:53</a></td></tr>
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
