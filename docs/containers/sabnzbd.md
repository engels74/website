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
<tr><td><div id="tag4951" onclick="CopyToClipboard('tag4951');return false;" class="tag-decoration">nightly</div><div id="tag11247" onclick="CopyToClipboard('tag11247');return false;" class="tag-decoration">nightly-4d39d7b</div><div id="tag15893" onclick="CopyToClipboard('tag15893');return false;" class="tag-decoration">nightly-4520de77ad3f8c8f9e6d886c9420ee468b79f31e</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/4d39d7b407cbfde1409212622aeccecc56f52312" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/31385215632" target="_blank">2026-08-10 11:49:36</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag26954" onclick="CopyToClipboard('tag26954');return false;" class="tag-decoration">release</div><div id="tag32522" onclick="CopyToClipboard('tag32522');return false;" class="tag-decoration">release-5f790bd</div><div id="tag1272" onclick="CopyToClipboard('tag1272');return false;" class="tag-decoration">release-5.0.4</div><div id="tag7001" onclick="CopyToClipboard('tag7001');return false;" class="tag-decoration">release-v5</div><div id="tag30617" onclick="CopyToClipboard('tag30617');return false;" class="tag-decoration">release-v5.0</div><div id="tag390" onclick="CopyToClipboard('tag390');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5f790bdb14f2be10d3bd4c9ab4b2c57e6ce00894" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395690614" target="_blank">2026-07-28 20:17:28</a></td></tr>
<tr><td><div id="tag14690" onclick="CopyToClipboard('tag14690');return false;" class="tag-decoration">testing</div><div id="tag31859" onclick="CopyToClipboard('tag31859');return false;" class="tag-decoration">testing-94ee6c5</div><div id="tag30004" onclick="CopyToClipboard('tag30004');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag29864" onclick="CopyToClipboard('tag29864');return false;" class="tag-decoration">testing-v5</div><div id="tag15818" onclick="CopyToClipboard('tag15818');return false;" class="tag-decoration">testing-v5.0</div><div id="tag16321" onclick="CopyToClipboard('tag16321');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/94ee6c563c8c0c85251526fc0ac61909d43225d7" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395681904" target="_blank">2026-07-28 20:17:20</a></td></tr>
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
