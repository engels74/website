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
<tr><td><div id="tag26925" onclick="CopyToClipboard('tag26925');return false;" class="tag-decoration">nightly</div><div id="tag21946" onclick="CopyToClipboard('tag21946');return false;" class="tag-decoration">nightly-79e3513</div><div id="tag3624" onclick="CopyToClipboard('tag3624');return false;" class="tag-decoration">nightly-d45a1d8bf088875b3f8d17481495e6bf80ec447f</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/79e3513621d2d4446d2af00b6ec32251fd488cce" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/31973317059" target="_blank">2026-08-16 21:22:48</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag4897" onclick="CopyToClipboard('tag4897');return false;" class="tag-decoration">release</div><div id="tag6152" onclick="CopyToClipboard('tag6152');return false;" class="tag-decoration">release-c7bcacb</div><div id="tag18130" onclick="CopyToClipboard('tag18130');return false;" class="tag-decoration">release-5.1.0</div><div id="tag14544" onclick="CopyToClipboard('tag14544');return false;" class="tag-decoration">release-v5</div><div id="tag300" onclick="CopyToClipboard('tag300');return false;" class="tag-decoration">release-v5.1</div><div id="tag29949" onclick="CopyToClipboard('tag29949');return false;" class="tag-decoration">release-v5.1.0</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/c7bcacb52c20d8c210aed182d4c17f41c59f53bf" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/31874749986" target="_blank">2026-08-15 08:32:45</a></td></tr>
<tr><td><div id="tag30521" onclick="CopyToClipboard('tag30521');return false;" class="tag-decoration">testing</div><div id="tag30684" onclick="CopyToClipboard('tag30684');return false;" class="tag-decoration">testing-ec434d2</div><div id="tag11419" onclick="CopyToClipboard('tag11419');return false;" class="tag-decoration">testing-5.1.0</div><div id="tag6981" onclick="CopyToClipboard('tag6981');return false;" class="tag-decoration">testing-v5</div><div id="tag6342" onclick="CopyToClipboard('tag6342');return false;" class="tag-decoration">testing-v5.1</div><div id="tag20381" onclick="CopyToClipboard('tag20381');return false;" class="tag-decoration">testing-v5.1.0</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/ec434d29941ef1b61bc3cf681c02b3155cf95f24" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/31874756277" target="_blank">2026-08-15 08:32:53</a></td></tr>
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
