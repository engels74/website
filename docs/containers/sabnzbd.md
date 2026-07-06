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
<tr><td><div id="tag7618" onclick="CopyToClipboard('tag7618');return false;" class="tag-decoration">nightly</div><div id="tag7691" onclick="CopyToClipboard('tag7691');return false;" class="tag-decoration">nightly-5284f61</div><div id="tag21626" onclick="CopyToClipboard('tag21626');return false;" class="tag-decoration">nightly-8afb8a91e29aaf8fc319c2f370e2b2611167a5f5</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/5284f610cd8b872887021b6ae7e511bf221feb58" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28792862580" target="_blank">2026-07-06 12:51:51</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag21194" onclick="CopyToClipboard('tag21194');return false;" class="tag-decoration">release</div><div id="tag10735" onclick="CopyToClipboard('tag10735');return false;" class="tag-decoration">release-5f895d5</div><div id="tag28428" onclick="CopyToClipboard('tag28428');return false;" class="tag-decoration">release-5.0.4</div><div id="tag5222" onclick="CopyToClipboard('tag5222');return false;" class="tag-decoration">release-v5</div><div id="tag6794" onclick="CopyToClipboard('tag6794');return false;" class="tag-decoration">release-v5.0</div><div id="tag25063" onclick="CopyToClipboard('tag25063');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5f895d55bff876b3ada4d917157eeb04ded7ccc4" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28596533894" target="_blank">2026-07-02 14:09:19</a></td></tr>
<tr><td><div id="tag28085" onclick="CopyToClipboard('tag28085');return false;" class="tag-decoration">testing</div><div id="tag10045" onclick="CopyToClipboard('tag10045');return false;" class="tag-decoration">testing-4c71f05</div><div id="tag23692" onclick="CopyToClipboard('tag23692');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag30567" onclick="CopyToClipboard('tag30567');return false;" class="tag-decoration">testing-v5</div><div id="tag21555" onclick="CopyToClipboard('tag21555');return false;" class="tag-decoration">testing-v5.0</div><div id="tag23538" onclick="CopyToClipboard('tag23538');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/4c71f05cc28313bfb31556bb9d28a2c7c7de987a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28596533446" target="_blank">2026-07-02 14:09:19</a></td></tr>
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
