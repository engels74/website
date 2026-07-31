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
<tr><td><div id="tag29566" onclick="CopyToClipboard('tag29566');return false;" class="tag-decoration">nightly</div><div id="tag25332" onclick="CopyToClipboard('tag25332');return false;" class="tag-decoration">nightly-616c66d</div><div id="tag7507" onclick="CopyToClipboard('tag7507');return false;" class="tag-decoration">nightly-dc5620a52c584484bef04a77fbc933234013372a</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/616c66d8f4ddf6b22fe436baf670868fbabf70db" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30610708111" target="_blank">2026-07-31 06:47:26</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag13267" onclick="CopyToClipboard('tag13267');return false;" class="tag-decoration">release</div><div id="tag18780" onclick="CopyToClipboard('tag18780');return false;" class="tag-decoration">release-5f790bd</div><div id="tag3043" onclick="CopyToClipboard('tag3043');return false;" class="tag-decoration">release-5.0.4</div><div id="tag14975" onclick="CopyToClipboard('tag14975');return false;" class="tag-decoration">release-v5</div><div id="tag31627" onclick="CopyToClipboard('tag31627');return false;" class="tag-decoration">release-v5.0</div><div id="tag15463" onclick="CopyToClipboard('tag15463');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5f790bdb14f2be10d3bd4c9ab4b2c57e6ce00894" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395690614" target="_blank">2026-07-28 20:17:28</a></td></tr>
<tr><td><div id="tag30641" onclick="CopyToClipboard('tag30641');return false;" class="tag-decoration">testing</div><div id="tag17488" onclick="CopyToClipboard('tag17488');return false;" class="tag-decoration">testing-94ee6c5</div><div id="tag402" onclick="CopyToClipboard('tag402');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag17899" onclick="CopyToClipboard('tag17899');return false;" class="tag-decoration">testing-v5</div><div id="tag12245" onclick="CopyToClipboard('tag12245');return false;" class="tag-decoration">testing-v5.0</div><div id="tag10801" onclick="CopyToClipboard('tag10801');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/94ee6c563c8c0c85251526fc0ac61909d43225d7" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395681904" target="_blank">2026-07-28 20:17:20</a></td></tr>
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
