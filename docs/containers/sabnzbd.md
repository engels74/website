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
<tr><td><div id="tag26924" onclick="CopyToClipboard('tag26924');return false;" class="tag-decoration">nightly</div><div id="tag20849" onclick="CopyToClipboard('tag20849');return false;" class="tag-decoration">nightly-e290288</div><div id="tag30423" onclick="CopyToClipboard('tag30423');return false;" class="tag-decoration">nightly-d7b7377b42763f7f656afe19c24472d4fb0aac14</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/e29028839618e9739f87342a699f548ea2d7fca4" target="_blank">Version update: 787c51fa8ed21bb59d3116464ea4933dcf4fc49d => d7b7377b42763f7f656afe19c24472d4fb0aac14</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22078497648" target="_blank">2026-02-16 21:50:29</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag23097" onclick="CopyToClipboard('tag23097');return false;" class="tag-decoration">release</div><div id="tag28627" onclick="CopyToClipboard('tag28627');return false;" class="tag-decoration">release-252442e</div><div id="tag15618" onclick="CopyToClipboard('tag15618');return false;" class="tag-decoration">release-4.5.5</div><div id="tag19392" onclick="CopyToClipboard('tag19392');return false;" class="tag-decoration">release-v4</div><div id="tag7859" onclick="CopyToClipboard('tag7859');return false;" class="tag-decoration">release-v4.5</div><div id="tag6091" onclick="CopyToClipboard('tag6091');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/252442ee081e7bffb07db68d74238fe65fe61492" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823272944" target="_blank">2026-02-09 11:29:10</a></td></tr>
<tr><td><div id="tag21355" onclick="CopyToClipboard('tag21355');return false;" class="tag-decoration">testing</div><div id="tag31869" onclick="CopyToClipboard('tag31869');return false;" class="tag-decoration">testing-3dc0cdf</div><div id="tag18074" onclick="CopyToClipboard('tag18074');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag17538" onclick="CopyToClipboard('tag17538');return false;" class="tag-decoration">testing-v4</div><div id="tag31921" onclick="CopyToClipboard('tag31921');return false;" class="tag-decoration">testing-v4.5</div><div id="tag16909" onclick="CopyToClipboard('tag16909');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3dc0cdf9be0128f86ab1d3137f11ee412fbc5fa6" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823273556" target="_blank">2026-02-09 11:29:12</a></td></tr>
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
