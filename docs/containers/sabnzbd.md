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
<tr><td><div id="tag30806" onclick="CopyToClipboard('tag30806');return false;" class="tag-decoration">nightly</div><div id="tag20268" onclick="CopyToClipboard('tag20268');return false;" class="tag-decoration">nightly-7b7d8b9</div><div id="tag13937" onclick="CopyToClipboard('tag13937');return false;" class="tag-decoration">nightly-40860c68cab10214ed6a0f9a3a45c8bebbde58b0</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/7b7d8b9c8e2a54e3f7fead33baeac2f97bd35c7f" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/31277182088" target="_blank">2026-08-08 20:33:15</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag13419" onclick="CopyToClipboard('tag13419');return false;" class="tag-decoration">release</div><div id="tag22587" onclick="CopyToClipboard('tag22587');return false;" class="tag-decoration">release-5f790bd</div><div id="tag24890" onclick="CopyToClipboard('tag24890');return false;" class="tag-decoration">release-5.0.4</div><div id="tag12515" onclick="CopyToClipboard('tag12515');return false;" class="tag-decoration">release-v5</div><div id="tag11509" onclick="CopyToClipboard('tag11509');return false;" class="tag-decoration">release-v5.0</div><div id="tag19155" onclick="CopyToClipboard('tag19155');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5f790bdb14f2be10d3bd4c9ab4b2c57e6ce00894" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395690614" target="_blank">2026-07-28 20:17:28</a></td></tr>
<tr><td><div id="tag28820" onclick="CopyToClipboard('tag28820');return false;" class="tag-decoration">testing</div><div id="tag31261" onclick="CopyToClipboard('tag31261');return false;" class="tag-decoration">testing-94ee6c5</div><div id="tag6858" onclick="CopyToClipboard('tag6858');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag648" onclick="CopyToClipboard('tag648');return false;" class="tag-decoration">testing-v5</div><div id="tag1576" onclick="CopyToClipboard('tag1576');return false;" class="tag-decoration">testing-v5.0</div><div id="tag22452" onclick="CopyToClipboard('tag22452');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/94ee6c563c8c0c85251526fc0ac61909d43225d7" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/30395681904" target="_blank">2026-07-28 20:17:20</a></td></tr>
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
