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
<tr><td><div id="tag15591" onclick="CopyToClipboard('tag15591');return false;" class="tag-decoration">nightly</div><div id="tag27039" onclick="CopyToClipboard('tag27039');return false;" class="tag-decoration">nightly-6f8fc72</div><div id="tag23454" onclick="CopyToClipboard('tag23454');return false;" class="tag-decoration">nightly-5b7a89ffb8a9287046e2fb02a803861f2db83369</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/6f8fc725ee1085c747f0aaaa564efd3ec145bac5" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29490000779" target="_blank">2026-07-16 10:12:30</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag18191" onclick="CopyToClipboard('tag18191');return false;" class="tag-decoration">release</div><div id="tag24010" onclick="CopyToClipboard('tag24010');return false;" class="tag-decoration">release-22b6faf</div><div id="tag21196" onclick="CopyToClipboard('tag21196');return false;" class="tag-decoration">release-5.0.4</div><div id="tag5300" onclick="CopyToClipboard('tag5300');return false;" class="tag-decoration">release-v5</div><div id="tag16262" onclick="CopyToClipboard('tag16262');return false;" class="tag-decoration">release-v5.0</div><div id="tag29816" onclick="CopyToClipboard('tag29816');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/22b6fafa41c0542d04f69e85ff0d1141ea314f3d" target="_blank">fix: move user bundle markers to user-bundles.d for s6-overlay >= 3.2.3.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29424697585" target="_blank">2026-07-15 14:41:34</a></td></tr>
<tr><td><div id="tag8786" onclick="CopyToClipboard('tag8786');return false;" class="tag-decoration">testing</div><div id="tag15761" onclick="CopyToClipboard('tag15761');return false;" class="tag-decoration">testing-1e4ca17</div><div id="tag4735" onclick="CopyToClipboard('tag4735');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag7803" onclick="CopyToClipboard('tag7803');return false;" class="tag-decoration">testing-v5</div><div id="tag31618" onclick="CopyToClipboard('tag31618');return false;" class="tag-decoration">testing-v5.0</div><div id="tag21339" onclick="CopyToClipboard('tag21339');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1e4ca177af138b56d90a850f38d042d76b5b9471" target="_blank">fix: move user bundle markers to user-bundles.d for s6-overlay >= 3.2.3.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29424701638" target="_blank">2026-07-15 14:41:38</a></td></tr>
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
