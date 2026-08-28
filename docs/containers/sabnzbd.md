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
<tr><td><div id="tag19712" onclick="CopyToClipboard('tag19712');return false;" class="tag-decoration">nightly</div><div id="tag18061" onclick="CopyToClipboard('tag18061');return false;" class="tag-decoration">nightly-4d88972</div><div id="tag11109" onclick="CopyToClipboard('tag11109');return false;" class="tag-decoration">nightly-e3bc15e8e6315fdcb55b94a7faa73c09d5f7e891</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/4d8897277b47863a74dae3e69999bc171e8bf1f1" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33178620667" target="_blank">2026-08-28 14:07:36</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag7564" onclick="CopyToClipboard('tag7564');return false;" class="tag-decoration">release</div><div id="tag13821" onclick="CopyToClipboard('tag13821');return false;" class="tag-decoration">release-3699da3</div><div id="tag17281" onclick="CopyToClipboard('tag17281');return false;" class="tag-decoration">release-5.1.2</div><div id="tag22063" onclick="CopyToClipboard('tag22063');return false;" class="tag-decoration">release-v5</div><div id="tag3115" onclick="CopyToClipboard('tag3115');return false;" class="tag-decoration">release-v5.1</div><div id="tag1614" onclick="CopyToClipboard('tag1614');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3699da399bd995c96fef64e914b2ef5e02caa282" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32919084624" target="_blank">2026-08-26 01:28:09</a></td></tr>
<tr><td><div id="tag6803" onclick="CopyToClipboard('tag6803');return false;" class="tag-decoration">testing</div><div id="tag32396" onclick="CopyToClipboard('tag32396');return false;" class="tag-decoration">testing-00935f0</div><div id="tag9895" onclick="CopyToClipboard('tag9895');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag16626" onclick="CopyToClipboard('tag16626');return false;" class="tag-decoration">testing-v5</div><div id="tag8409" onclick="CopyToClipboard('tag8409');return false;" class="tag-decoration">testing-v5.1</div><div id="tag21819" onclick="CopyToClipboard('tag21819');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/00935f0d6744379ad94969d7f14fa72e46fe68c7" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32919082616" target="_blank">2026-08-26 01:28:07</a></td></tr>
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
