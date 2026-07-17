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
<tr><td><div id="tag23339" onclick="CopyToClipboard('tag23339');return false;" class="tag-decoration">nightly</div><div id="tag5139" onclick="CopyToClipboard('tag5139');return false;" class="tag-decoration">nightly-3ee9924</div><div id="tag18048" onclick="CopyToClipboard('tag18048');return false;" class="tag-decoration">nightly-636aa91e213b89218a3bea9ae4fc2b57433f9737</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/3ee9924630fbe3a3c6f22db57e0cc5c142d72877" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29562746042" target="_blank">2026-07-17 07:19:48</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag201" onclick="CopyToClipboard('tag201');return false;" class="tag-decoration">release</div><div id="tag6002" onclick="CopyToClipboard('tag6002');return false;" class="tag-decoration">release-e4d88ea</div><div id="tag14479" onclick="CopyToClipboard('tag14479');return false;" class="tag-decoration">release-5.0.4</div><div id="tag24337" onclick="CopyToClipboard('tag24337');return false;" class="tag-decoration">release-v5</div><div id="tag5589" onclick="CopyToClipboard('tag5589');return false;" class="tag-decoration">release-v5.0</div><div id="tag4049" onclick="CopyToClipboard('tag4049');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/e4d88eaa0bfa608eb5869477cfa6f834660b119e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29489996210" target="_blank">2026-07-16 10:12:26</a></td></tr>
<tr><td><div id="tag29077" onclick="CopyToClipboard('tag29077');return false;" class="tag-decoration">testing</div><div id="tag16490" onclick="CopyToClipboard('tag16490');return false;" class="tag-decoration">testing-7336589</div><div id="tag28601" onclick="CopyToClipboard('tag28601');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag30648" onclick="CopyToClipboard('tag30648');return false;" class="tag-decoration">testing-v5</div><div id="tag11627" onclick="CopyToClipboard('tag11627');return false;" class="tag-decoration">testing-v5.0</div><div id="tag27409" onclick="CopyToClipboard('tag27409');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7336589951f67b55cde564e1a07a1e94d19f0c6e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29489995661" target="_blank">2026-07-16 10:12:24</a></td></tr>
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
