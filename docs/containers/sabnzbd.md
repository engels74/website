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
<tr><td><div id="tag6813" onclick="CopyToClipboard('tag6813');return false;" class="tag-decoration">nightly</div><div id="tag906" onclick="CopyToClipboard('tag906');return false;" class="tag-decoration">nightly-79e3513</div><div id="tag5856" onclick="CopyToClipboard('tag5856');return false;" class="tag-decoration">nightly-d45a1d8bf088875b3f8d17481495e6bf80ec447f</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/79e3513621d2d4446d2af00b6ec32251fd488cce" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/31973317059" target="_blank">2026-08-16 21:22:48</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag32096" onclick="CopyToClipboard('tag32096');return false;" class="tag-decoration">release</div><div id="tag174" onclick="CopyToClipboard('tag174');return false;" class="tag-decoration">release-c7bcacb</div><div id="tag9800" onclick="CopyToClipboard('tag9800');return false;" class="tag-decoration">release-5.1.0</div><div id="tag2236" onclick="CopyToClipboard('tag2236');return false;" class="tag-decoration">release-v5</div><div id="tag22093" onclick="CopyToClipboard('tag22093');return false;" class="tag-decoration">release-v5.1</div><div id="tag5266" onclick="CopyToClipboard('tag5266');return false;" class="tag-decoration">release-v5.1.0</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/c7bcacb52c20d8c210aed182d4c17f41c59f53bf" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/31874749986" target="_blank">2026-08-15 08:32:45</a></td></tr>
<tr><td><div id="tag15340" onclick="CopyToClipboard('tag15340');return false;" class="tag-decoration">testing</div><div id="tag2273" onclick="CopyToClipboard('tag2273');return false;" class="tag-decoration">testing-84603fa</div><div id="tag1954" onclick="CopyToClipboard('tag1954');return false;" class="tag-decoration">testing-5.1.0</div><div id="tag25462" onclick="CopyToClipboard('tag25462');return false;" class="tag-decoration">testing-v5</div><div id="tag6238" onclick="CopyToClipboard('tag6238');return false;" class="tag-decoration">testing-v5.1</div><div id="tag28400" onclick="CopyToClipboard('tag28400');return false;" class="tag-decoration">testing-v5.1.0</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/84603fa54d4f7453629f9ef31afb00046e524165" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32045977696" target="_blank">2026-08-17 16:31:10</a></td></tr>
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
