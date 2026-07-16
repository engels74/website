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
<tr><td><div id="tag12292" onclick="CopyToClipboard('tag12292');return false;" class="tag-decoration">nightly</div><div id="tag17344" onclick="CopyToClipboard('tag17344');return false;" class="tag-decoration">nightly-9386950</div><div id="tag27444" onclick="CopyToClipboard('tag27444');return false;" class="tag-decoration">nightly-a1c9a8aab1cd39a8635e23f0e47a04dafed19153</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/9386950824ebfe68adae3db5cad64e787b5e4f00" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29534585651" target="_blank">2026-07-16 21:03:48</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag16696" onclick="CopyToClipboard('tag16696');return false;" class="tag-decoration">release</div><div id="tag5006" onclick="CopyToClipboard('tag5006');return false;" class="tag-decoration">release-e4d88ea</div><div id="tag3763" onclick="CopyToClipboard('tag3763');return false;" class="tag-decoration">release-5.0.4</div><div id="tag26224" onclick="CopyToClipboard('tag26224');return false;" class="tag-decoration">release-v5</div><div id="tag28405" onclick="CopyToClipboard('tag28405');return false;" class="tag-decoration">release-v5.0</div><div id="tag13140" onclick="CopyToClipboard('tag13140');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/e4d88eaa0bfa608eb5869477cfa6f834660b119e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29489996210" target="_blank">2026-07-16 10:12:26</a></td></tr>
<tr><td><div id="tag19884" onclick="CopyToClipboard('tag19884');return false;" class="tag-decoration">testing</div><div id="tag19089" onclick="CopyToClipboard('tag19089');return false;" class="tag-decoration">testing-7336589</div><div id="tag22828" onclick="CopyToClipboard('tag22828');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag838" onclick="CopyToClipboard('tag838');return false;" class="tag-decoration">testing-v5</div><div id="tag11193" onclick="CopyToClipboard('tag11193');return false;" class="tag-decoration">testing-v5.0</div><div id="tag737" onclick="CopyToClipboard('tag737');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7336589951f67b55cde564e1a07a1e94d19f0c6e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29489995661" target="_blank">2026-07-16 10:12:24</a></td></tr>
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
