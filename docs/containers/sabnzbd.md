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
<tr><td><div id="tag4538" onclick="CopyToClipboard('tag4538');return false;" class="tag-decoration">nightly</div><div id="tag24814" onclick="CopyToClipboard('tag24814');return false;" class="tag-decoration">nightly-c86333c</div><div id="tag8739" onclick="CopyToClipboard('tag8739');return false;" class="tag-decoration">nightly-adde7b961cdc21bfd43b4221209c895d8c788e8c</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/c86333c2349cde44ff8947cf05003600c4b10578" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32144141644" target="_blank">2026-08-18 13:44:40</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag25158" onclick="CopyToClipboard('tag25158');return false;" class="tag-decoration">release</div><div id="tag4676" onclick="CopyToClipboard('tag4676');return false;" class="tag-decoration">release-7d0b5f6</div><div id="tag262" onclick="CopyToClipboard('tag262');return false;" class="tag-decoration">release-5.1.0</div><div id="tag10523" onclick="CopyToClipboard('tag10523');return false;" class="tag-decoration">release-v5</div><div id="tag27389" onclick="CopyToClipboard('tag27389');return false;" class="tag-decoration">release-v5.1</div><div id="tag28161" onclick="CopyToClipboard('tag28161');return false;" class="tag-decoration">release-v5.1.0</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7d0b5f6ebb5ed636f0d0d3e33058cf42f6a8171f" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32045975836" target="_blank">2026-08-17 16:31:08</a></td></tr>
<tr><td><div id="tag9672" onclick="CopyToClipboard('tag9672');return false;" class="tag-decoration">testing</div><div id="tag17559" onclick="CopyToClipboard('tag17559');return false;" class="tag-decoration">testing-84603fa</div><div id="tag21506" onclick="CopyToClipboard('tag21506');return false;" class="tag-decoration">testing-5.1.0</div><div id="tag16042" onclick="CopyToClipboard('tag16042');return false;" class="tag-decoration">testing-v5</div><div id="tag24300" onclick="CopyToClipboard('tag24300');return false;" class="tag-decoration">testing-v5.1</div><div id="tag166" onclick="CopyToClipboard('tag166');return false;" class="tag-decoration">testing-v5.1.0</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/84603fa54d4f7453629f9ef31afb00046e524165" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32045977696" target="_blank">2026-08-17 16:31:10</a></td></tr>
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
