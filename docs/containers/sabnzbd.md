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
<tr><td><div id="tag15930" onclick="CopyToClipboard('tag15930');return false;" class="tag-decoration">nightly</div><div id="tag27329" onclick="CopyToClipboard('tag27329');return false;" class="tag-decoration">nightly-10a180b</div><div id="tag29255" onclick="CopyToClipboard('tag29255');return false;" class="tag-decoration">nightly-0c3464e6a2fb36dc2f3b30a049c78edbc83a05d5</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/10a180b8b54c69ea442614cb7062f084fc1b4652" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/31031280695" target="_blank">2026-08-05 17:42:29</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag20671" onclick="CopyToClipboard('tag20671');return false;" class="tag-decoration">release</div><div id="tag6383" onclick="CopyToClipboard('tag6383');return false;" class="tag-decoration">release-5f790bd</div><div id="tag5224" onclick="CopyToClipboard('tag5224');return false;" class="tag-decoration">release-5.0.4</div><div id="tag20754" onclick="CopyToClipboard('tag20754');return false;" class="tag-decoration">release-v5</div><div id="tag27888" onclick="CopyToClipboard('tag27888');return false;" class="tag-decoration">release-v5.0</div><div id="tag14776" onclick="CopyToClipboard('tag14776');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5f790bdb14f2be10d3bd4c9ab4b2c57e6ce00894" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395690614" target="_blank">2026-07-28 20:17:28</a></td></tr>
<tr><td><div id="tag16723" onclick="CopyToClipboard('tag16723');return false;" class="tag-decoration">testing</div><div id="tag21852" onclick="CopyToClipboard('tag21852');return false;" class="tag-decoration">testing-94ee6c5</div><div id="tag25456" onclick="CopyToClipboard('tag25456');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag17256" onclick="CopyToClipboard('tag17256');return false;" class="tag-decoration">testing-v5</div><div id="tag24857" onclick="CopyToClipboard('tag24857');return false;" class="tag-decoration">testing-v5.0</div><div id="tag2183" onclick="CopyToClipboard('tag2183');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/94ee6c563c8c0c85251526fc0ac61909d43225d7" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395681904" target="_blank">2026-07-28 20:17:20</a></td></tr>
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
