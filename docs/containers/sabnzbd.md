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
<tr><td><div id="tag4125" onclick="CopyToClipboard('tag4125');return false;" class="tag-decoration">nightly</div><div id="tag2753" onclick="CopyToClipboard('tag2753');return false;" class="tag-decoration">nightly-925b21c</div><div id="tag7544" onclick="CopyToClipboard('tag7544');return false;" class="tag-decoration">nightly-5b7a89ffb8a9287046e2fb02a803861f2db83369</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/925b21cd5547f9fbdae5ddf74cfa9ed623f8743c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29479792202" target="_blank">2026-07-16 07:23:57</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag7160" onclick="CopyToClipboard('tag7160');return false;" class="tag-decoration">release</div><div id="tag13247" onclick="CopyToClipboard('tag13247');return false;" class="tag-decoration">release-22b6faf</div><div id="tag7511" onclick="CopyToClipboard('tag7511');return false;" class="tag-decoration">release-5.0.4</div><div id="tag268" onclick="CopyToClipboard('tag268');return false;" class="tag-decoration">release-v5</div><div id="tag13682" onclick="CopyToClipboard('tag13682');return false;" class="tag-decoration">release-v5.0</div><div id="tag5558" onclick="CopyToClipboard('tag5558');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/22b6fafa41c0542d04f69e85ff0d1141ea314f3d" target="_blank">fix: move user bundle markers to user-bundles.d for s6-overlay >= 3.2.3.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29424697585" target="_blank">2026-07-15 14:41:34</a></td></tr>
<tr><td><div id="tag1750" onclick="CopyToClipboard('tag1750');return false;" class="tag-decoration">testing</div><div id="tag20451" onclick="CopyToClipboard('tag20451');return false;" class="tag-decoration">testing-1e4ca17</div><div id="tag16430" onclick="CopyToClipboard('tag16430');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag4339" onclick="CopyToClipboard('tag4339');return false;" class="tag-decoration">testing-v5</div><div id="tag13710" onclick="CopyToClipboard('tag13710');return false;" class="tag-decoration">testing-v5.0</div><div id="tag32591" onclick="CopyToClipboard('tag32591');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1e4ca177af138b56d90a850f38d042d76b5b9471" target="_blank">fix: move user bundle markers to user-bundles.d for s6-overlay >= 3.2.3.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29424701638" target="_blank">2026-07-15 14:41:38</a></td></tr>
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
