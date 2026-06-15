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
<tr><td><div id="tag26486" onclick="CopyToClipboard('tag26486');return false;" class="tag-decoration">nightly</div><div id="tag22167" onclick="CopyToClipboard('tag22167');return false;" class="tag-decoration">nightly-d1615e3</div><div id="tag14977" onclick="CopyToClipboard('tag14977');return false;" class="tag-decoration">nightly-8919aa7ec0147969e1ad4e5cedb449bfe4080695</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/d1615e3a71c7546e00e25dbb3088533fe2b73a89" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27549091030" target="_blank">2026-06-15 13:19:25</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag15698" onclick="CopyToClipboard('tag15698');return false;" class="tag-decoration">release</div><div id="tag12822" onclick="CopyToClipboard('tag12822');return false;" class="tag-decoration">release-746e018</div><div id="tag27002" onclick="CopyToClipboard('tag27002');return false;" class="tag-decoration">release-5.0.4</div><div id="tag26126" onclick="CopyToClipboard('tag26126');return false;" class="tag-decoration">release-v5</div><div id="tag30552" onclick="CopyToClipboard('tag30552');return false;" class="tag-decoration">release-v5.0</div><div id="tag2064" onclick="CopyToClipboard('tag2064');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/746e018cd50910dae73acbd4ab2ae90183233d6c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354913378" target="_blank">2026-06-11 14:40:57</a></td></tr>
<tr><td><div id="tag22449" onclick="CopyToClipboard('tag22449');return false;" class="tag-decoration">testing</div><div id="tag4271" onclick="CopyToClipboard('tag4271');return false;" class="tag-decoration">testing-1b1942e</div><div id="tag23294" onclick="CopyToClipboard('tag23294');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag6097" onclick="CopyToClipboard('tag6097');return false;" class="tag-decoration">testing-v5</div><div id="tag17038" onclick="CopyToClipboard('tag17038');return false;" class="tag-decoration">testing-v5.0</div><div id="tag3777" onclick="CopyToClipboard('tag3777');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1b1942e349033b72b39f15958dc0694493b2d37d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354916499" target="_blank">2026-06-11 14:40:59</a></td></tr>
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
