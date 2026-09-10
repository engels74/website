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
<tr><td><div id="tag7618" onclick="CopyToClipboard('tag7618');return false;" class="tag-decoration">nightly</div><div id="tag8262" onclick="CopyToClipboard('tag8262');return false;" class="tag-decoration">nightly-303f2ac</div><div id="tag22556" onclick="CopyToClipboard('tag22556');return false;" class="tag-decoration">nightly-cfde583ccc1896ef8aa32bc05961c3cefbdaa5d3</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/303f2ac99b54ed0bf517800f0fc3cf0a47542e1e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34482508358" target="_blank">2026-09-10 13:25:02</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag4036" onclick="CopyToClipboard('tag4036');return false;" class="tag-decoration">release</div><div id="tag29392" onclick="CopyToClipboard('tag29392');return false;" class="tag-decoration">release-7f49c81</div><div id="tag8182" onclick="CopyToClipboard('tag8182');return false;" class="tag-decoration">release-5.1.3</div><div id="tag27332" onclick="CopyToClipboard('tag27332');return false;" class="tag-decoration">release-v5</div><div id="tag4665" onclick="CopyToClipboard('tag4665');return false;" class="tag-decoration">release-v5.1</div><div id="tag25867" onclick="CopyToClipboard('tag25867');return false;" class="tag-decoration">release-v5.1.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7f49c8193cfd6e4bfb7d1d5f6ec8325d3ab09c27" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34482526229" target="_blank">2026-09-10 13:25:12</a></td></tr>
<tr><td><div id="tag6645" onclick="CopyToClipboard('tag6645');return false;" class="tag-decoration">testing</div><div id="tag31444" onclick="CopyToClipboard('tag31444');return false;" class="tag-decoration">testing-edc1903</div><div id="tag7963" onclick="CopyToClipboard('tag7963');return false;" class="tag-decoration">testing-5.1.3</div><div id="tag13156" onclick="CopyToClipboard('tag13156');return false;" class="tag-decoration">testing-v5</div><div id="tag21218" onclick="CopyToClipboard('tag21218');return false;" class="tag-decoration">testing-v5.1</div><div id="tag17914" onclick="CopyToClipboard('tag17914');return false;" class="tag-decoration">testing-v5.1.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/edc190356ebe08952bc00d0e0fa97177aec9163d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34418972124" target="_blank">2026-09-09 23:54:38</a></td></tr>
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
