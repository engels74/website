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
<tr><td><div id="tag23705" onclick="CopyToClipboard('tag23705');return false;" class="tag-decoration">nightly</div><div id="tag7776" onclick="CopyToClipboard('tag7776');return false;" class="tag-decoration">nightly-60ed37d</div><div id="tag1089" onclick="CopyToClipboard('tag1089');return false;" class="tag-decoration">nightly-60f555117c78466704bcb82b22cc5027944e8139</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/60ed37d2e27aa0131f5d1cf796b81258a6135e21" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25925941112" target="_blank">2026-05-15 15:22:41</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag17309" onclick="CopyToClipboard('tag17309');return false;" class="tag-decoration">release</div><div id="tag23630" onclick="CopyToClipboard('tag23630');return false;" class="tag-decoration">release-5cde00f</div><div id="tag12226" onclick="CopyToClipboard('tag12226');return false;" class="tag-decoration">release-5.0.3</div><div id="tag14321" onclick="CopyToClipboard('tag14321');return false;" class="tag-decoration">release-v5</div><div id="tag18674" onclick="CopyToClipboard('tag18674');return false;" class="tag-decoration">release-v5.0</div><div id="tag10228" onclick="CopyToClipboard('tag10228');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5cde00fb9e68b414c8c07d3ec49b7697fdc1424b" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25925933814" target="_blank">2026-05-15 15:22:32</a></td></tr>
<tr><td><div id="tag2" onclick="CopyToClipboard('tag2');return false;" class="tag-decoration">testing</div><div id="tag7858" onclick="CopyToClipboard('tag7858');return false;" class="tag-decoration">testing-af66d6f</div><div id="tag15014" onclick="CopyToClipboard('tag15014');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag1536" onclick="CopyToClipboard('tag1536');return false;" class="tag-decoration">testing-v5</div><div id="tag11059" onclick="CopyToClipboard('tag11059');return false;" class="tag-decoration">testing-v5.0</div><div id="tag5771" onclick="CopyToClipboard('tag5771');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/af66d6fffe436c78f9fde0b2f793e40f60acbc26" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25925933927" target="_blank">2026-05-15 15:22:33</a></td></tr>
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
