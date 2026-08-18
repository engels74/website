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
<tr><td><div id="tag8992" onclick="CopyToClipboard('tag8992');return false;" class="tag-decoration">nightly</div><div id="tag22265" onclick="CopyToClipboard('tag22265');return false;" class="tag-decoration">nightly-c86333c</div><div id="tag23289" onclick="CopyToClipboard('tag23289');return false;" class="tag-decoration">nightly-adde7b961cdc21bfd43b4221209c895d8c788e8c</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/c86333c2349cde44ff8947cf05003600c4b10578" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32144141644" target="_blank">2026-08-18 13:44:40</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag22976" onclick="CopyToClipboard('tag22976');return false;" class="tag-decoration">release</div><div id="tag23276" onclick="CopyToClipboard('tag23276');return false;" class="tag-decoration">release-1f36d8f</div><div id="tag24395" onclick="CopyToClipboard('tag24395');return false;" class="tag-decoration">release-5.1.0</div><div id="tag9795" onclick="CopyToClipboard('tag9795');return false;" class="tag-decoration">release-v5</div><div id="tag14112" onclick="CopyToClipboard('tag14112');return false;" class="tag-decoration">release-v5.1</div><div id="tag5087" onclick="CopyToClipboard('tag5087');return false;" class="tag-decoration">release-v5.1.0</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1f36d8f8117dacb507350295da9c729831ed243c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32144139479" target="_blank">2026-08-18 13:44:38</a></td></tr>
<tr><td><div id="tag13702" onclick="CopyToClipboard('tag13702');return false;" class="tag-decoration">testing</div><div id="tag23396" onclick="CopyToClipboard('tag23396');return false;" class="tag-decoration">testing-9f1ec6e</div><div id="tag19251" onclick="CopyToClipboard('tag19251');return false;" class="tag-decoration">testing-5.1.0</div><div id="tag1309" onclick="CopyToClipboard('tag1309');return false;" class="tag-decoration">testing-v5</div><div id="tag2604" onclick="CopyToClipboard('tag2604');return false;" class="tag-decoration">testing-v5.1</div><div id="tag9428" onclick="CopyToClipboard('tag9428');return false;" class="tag-decoration">testing-v5.1.0</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/9f1ec6e81ff3a769acf33049c8626b20054d4413" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32144141240" target="_blank">2026-08-18 13:44:39</a></td></tr>
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
