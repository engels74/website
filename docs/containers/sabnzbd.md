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
<tr><td><div id="tag11022" onclick="CopyToClipboard('tag11022');return false;" class="tag-decoration">nightly</div><div id="tag26083" onclick="CopyToClipboard('tag26083');return false;" class="tag-decoration">nightly-a59880e</div><div id="tag30980" onclick="CopyToClipboard('tag30980');return false;" class="tag-decoration">nightly-777db2015828fca63582d21b0e756fae21c1d80e</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/a59880e66c6fe74ef6283c96344c654c82b87561" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354914900" target="_blank">2026-06-11 14:40:55</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag3772" onclick="CopyToClipboard('tag3772');return false;" class="tag-decoration">release</div><div id="tag10230" onclick="CopyToClipboard('tag10230');return false;" class="tag-decoration">release-746e018</div><div id="tag14539" onclick="CopyToClipboard('tag14539');return false;" class="tag-decoration">release-5.0.4</div><div id="tag23837" onclick="CopyToClipboard('tag23837');return false;" class="tag-decoration">release-v5</div><div id="tag11776" onclick="CopyToClipboard('tag11776');return false;" class="tag-decoration">release-v5.0</div><div id="tag5618" onclick="CopyToClipboard('tag5618');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/746e018cd50910dae73acbd4ab2ae90183233d6c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354913378" target="_blank">2026-06-11 14:40:57</a></td></tr>
<tr><td><div id="tag29687" onclick="CopyToClipboard('tag29687');return false;" class="tag-decoration">testing</div><div id="tag19482" onclick="CopyToClipboard('tag19482');return false;" class="tag-decoration">testing-1b1942e</div><div id="tag12369" onclick="CopyToClipboard('tag12369');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag25324" onclick="CopyToClipboard('tag25324');return false;" class="tag-decoration">testing-v5</div><div id="tag14878" onclick="CopyToClipboard('tag14878');return false;" class="tag-decoration">testing-v5.0</div><div id="tag10777" onclick="CopyToClipboard('tag10777');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1b1942e349033b72b39f15958dc0694493b2d37d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354916499" target="_blank">2026-06-11 14:40:59</a></td></tr>
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
