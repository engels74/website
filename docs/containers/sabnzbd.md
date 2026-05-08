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
<tr><td><div id="tag12237" onclick="CopyToClipboard('tag12237');return false;" class="tag-decoration">nightly</div><div id="tag19604" onclick="CopyToClipboard('tag19604');return false;" class="tag-decoration">nightly-f4533fb</div><div id="tag18524" onclick="CopyToClipboard('tag18524');return false;" class="tag-decoration">nightly-2668f1cd267ce13722c9f695337a8f7d134f3fba</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/f4533fb77b5459ee5fcc560830ca55dc24599651" target="_blank">Version update: 9d7ab5368590daab11723428c7e73e26c8cae055 => 2668f1cd267ce13722c9f695337a8f7d134f3fba</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25544522951" target="_blank">2026-05-08 08:04:30</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag14236" onclick="CopyToClipboard('tag14236');return false;" class="tag-decoration">release</div><div id="tag21224" onclick="CopyToClipboard('tag21224');return false;" class="tag-decoration">release-8d79706</div><div id="tag17089" onclick="CopyToClipboard('tag17089');return false;" class="tag-decoration">release-5.0.1</div><div id="tag21554" onclick="CopyToClipboard('tag21554');return false;" class="tag-decoration">release-v5</div><div id="tag14229" onclick="CopyToClipboard('tag14229');return false;" class="tag-decoration">release-v5.0</div><div id="tag19814" onclick="CopyToClipboard('tag19814');return false;" class="tag-decoration">release-v5.0.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8d7970682214e86f4df593db68c24b605a1a5718" target="_blank">Version update: 5.0.0 => 5.0.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25234254172" target="_blank">2026-05-01 21:37:08</a></td></tr>
<tr><td><div id="tag7968" onclick="CopyToClipboard('tag7968');return false;" class="tag-decoration">testing</div><div id="tag840" onclick="CopyToClipboard('tag840');return false;" class="tag-decoration">testing-2b55556</div><div id="tag6562" onclick="CopyToClipboard('tag6562');return false;" class="tag-decoration">testing-5.0.1</div><div id="tag17977" onclick="CopyToClipboard('tag17977');return false;" class="tag-decoration">testing-v5</div><div id="tag18336" onclick="CopyToClipboard('tag18336');return false;" class="tag-decoration">testing-v5.0</div><div id="tag3242" onclick="CopyToClipboard('tag3242');return false;" class="tag-decoration">testing-v5.0.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2b5555662f7d34c27829058643eff45c1b6eee87" target="_blank">Version update: 5.0.0 => 5.0.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25234254956" target="_blank">2026-05-01 21:37:10</a></td></tr>
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
