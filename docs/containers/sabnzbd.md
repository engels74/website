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
<tr><td><div id="tag10221" onclick="CopyToClipboard('tag10221');return false;" class="tag-decoration">nightly</div><div id="tag20111" onclick="CopyToClipboard('tag20111');return false;" class="tag-decoration">nightly-f98cd5f</div><div id="tag17859" onclick="CopyToClipboard('tag17859');return false;" class="tag-decoration">nightly-d9cd7a72b119873e5728b7abdd528acd12ef8c34</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/f98cd5fdacf1437d1175c319ab00b5e6f39b9e1b" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28472795673" target="_blank">2026-06-30 20:11:28</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag27497" onclick="CopyToClipboard('tag27497');return false;" class="tag-decoration">release</div><div id="tag12201" onclick="CopyToClipboard('tag12201');return false;" class="tag-decoration">release-b30cf3c</div><div id="tag28410" onclick="CopyToClipboard('tag28410');return false;" class="tag-decoration">release-5.0.4</div><div id="tag12315" onclick="CopyToClipboard('tag12315');return false;" class="tag-decoration">release-v5</div><div id="tag30126" onclick="CopyToClipboard('tag30126');return false;" class="tag-decoration">release-v5.0</div><div id="tag13255" onclick="CopyToClipboard('tag13255');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/b30cf3c8436673dc4b51fa0315c11553e8c8fac3" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28443343553" target="_blank">2026-06-30 12:12:17</a></td></tr>
<tr><td><div id="tag2722" onclick="CopyToClipboard('tag2722');return false;" class="tag-decoration">testing</div><div id="tag1521" onclick="CopyToClipboard('tag1521');return false;" class="tag-decoration">testing-870b377</div><div id="tag27054" onclick="CopyToClipboard('tag27054');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag23234" onclick="CopyToClipboard('tag23234');return false;" class="tag-decoration">testing-v5</div><div id="tag1183" onclick="CopyToClipboard('tag1183');return false;" class="tag-decoration">testing-v5.0</div><div id="tag6861" onclick="CopyToClipboard('tag6861');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/870b377c1295fdbbf529f0a4b1273c6b13c6f2ba" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28443343320" target="_blank">2026-06-30 12:12:17</a></td></tr>
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
