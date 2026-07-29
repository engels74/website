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
<tr><td><div id="tag30231" onclick="CopyToClipboard('tag30231');return false;" class="tag-decoration">nightly</div><div id="tag27505" onclick="CopyToClipboard('tag27505');return false;" class="tag-decoration">nightly-aafe72e</div><div id="tag24082" onclick="CopyToClipboard('tag24082');return false;" class="tag-decoration">nightly-eb9229d32664eee60aa66e4b571e9e4f8c628797</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/aafe72ead4fd04670b99d0fd51a0fe5ecc5afb19" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30490592528" target="_blank">2026-07-29 20:59:20</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag25140" onclick="CopyToClipboard('tag25140');return false;" class="tag-decoration">release</div><div id="tag12805" onclick="CopyToClipboard('tag12805');return false;" class="tag-decoration">release-5f790bd</div><div id="tag27017" onclick="CopyToClipboard('tag27017');return false;" class="tag-decoration">release-5.0.4</div><div id="tag25376" onclick="CopyToClipboard('tag25376');return false;" class="tag-decoration">release-v5</div><div id="tag20527" onclick="CopyToClipboard('tag20527');return false;" class="tag-decoration">release-v5.0</div><div id="tag28865" onclick="CopyToClipboard('tag28865');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5f790bdb14f2be10d3bd4c9ab4b2c57e6ce00894" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395690614" target="_blank">2026-07-28 20:17:28</a></td></tr>
<tr><td><div id="tag500" onclick="CopyToClipboard('tag500');return false;" class="tag-decoration">testing</div><div id="tag16563" onclick="CopyToClipboard('tag16563');return false;" class="tag-decoration">testing-94ee6c5</div><div id="tag24507" onclick="CopyToClipboard('tag24507');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag15010" onclick="CopyToClipboard('tag15010');return false;" class="tag-decoration">testing-v5</div><div id="tag24301" onclick="CopyToClipboard('tag24301');return false;" class="tag-decoration">testing-v5.0</div><div id="tag13066" onclick="CopyToClipboard('tag13066');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/94ee6c563c8c0c85251526fc0ac61909d43225d7" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395681904" target="_blank">2026-07-28 20:17:20</a></td></tr>
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
