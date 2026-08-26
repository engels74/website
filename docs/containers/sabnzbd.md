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
<tr><td><div id="tag8851" onclick="CopyToClipboard('tag8851');return false;" class="tag-decoration">nightly</div><div id="tag23579" onclick="CopyToClipboard('tag23579');return false;" class="tag-decoration">nightly-2e3e973</div><div id="tag6028" onclick="CopyToClipboard('tag6028');return false;" class="tag-decoration">nightly-f498147189f325393c5b762279b8cf708aa37e56</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/2e3e973f32eb42299986cab77899069bb4e35acc" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32919086249" target="_blank">2026-08-26 01:28:11</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag25536" onclick="CopyToClipboard('tag25536');return false;" class="tag-decoration">release</div><div id="tag25696" onclick="CopyToClipboard('tag25696');return false;" class="tag-decoration">release-9ea1119</div><div id="tag25683" onclick="CopyToClipboard('tag25683');return false;" class="tag-decoration">release-5.1.2</div><div id="tag4259" onclick="CopyToClipboard('tag4259');return false;" class="tag-decoration">release-v5</div><div id="tag13878" onclick="CopyToClipboard('tag13878');return false;" class="tag-decoration">release-v5.1</div><div id="tag24376" onclick="CopyToClipboard('tag24376');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/9ea11196defff1c60c1f20baca9f92c7e73d9317" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32861952518" target="_blank">2026-08-25 14:49:40</a></td></tr>
<tr><td><div id="tag22226" onclick="CopyToClipboard('tag22226');return false;" class="tag-decoration">testing</div><div id="tag13103" onclick="CopyToClipboard('tag13103');return false;" class="tag-decoration">testing-00935f0</div><div id="tag22339" onclick="CopyToClipboard('tag22339');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag25200" onclick="CopyToClipboard('tag25200');return false;" class="tag-decoration">testing-v5</div><div id="tag14019" onclick="CopyToClipboard('tag14019');return false;" class="tag-decoration">testing-v5.1</div><div id="tag15820" onclick="CopyToClipboard('tag15820');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/00935f0d6744379ad94969d7f14fa72e46fe68c7" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32919082616" target="_blank">2026-08-26 01:28:07</a></td></tr>
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
