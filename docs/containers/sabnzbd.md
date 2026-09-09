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
<tr><td><div id="tag9502" onclick="CopyToClipboard('tag9502');return false;" class="tag-decoration">nightly</div><div id="tag4439" onclick="CopyToClipboard('tag4439');return false;" class="tag-decoration">nightly-1426957</div><div id="tag30756" onclick="CopyToClipboard('tag30756');return false;" class="tag-decoration">nightly-29699890d5d55b83680d679e18aa734d90663b07</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/14269577e35c4bd678223b9896d237c5f2382eb1" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34418964867" target="_blank">2026-09-09 23:54:31</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag2535" onclick="CopyToClipboard('tag2535');return false;" class="tag-decoration">release</div><div id="tag31009" onclick="CopyToClipboard('tag31009');return false;" class="tag-decoration">release-b508315</div><div id="tag28244" onclick="CopyToClipboard('tag28244');return false;" class="tag-decoration">release-5.1.3</div><div id="tag23813" onclick="CopyToClipboard('tag23813');return false;" class="tag-decoration">release-v5</div><div id="tag17445" onclick="CopyToClipboard('tag17445');return false;" class="tag-decoration">release-v5.1</div><div id="tag4423" onclick="CopyToClipboard('tag4423');return false;" class="tag-decoration">release-v5.1.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/b508315f96fffa35e1a79a9ed142e4fe4e711526" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34418970422" target="_blank">2026-09-09 23:54:36</a></td></tr>
<tr><td><div id="tag7032" onclick="CopyToClipboard('tag7032');return false;" class="tag-decoration">testing</div><div id="tag14138" onclick="CopyToClipboard('tag14138');return false;" class="tag-decoration">testing-edc1903</div><div id="tag12404" onclick="CopyToClipboard('tag12404');return false;" class="tag-decoration">testing-5.1.3</div><div id="tag25956" onclick="CopyToClipboard('tag25956');return false;" class="tag-decoration">testing-v5</div><div id="tag9946" onclick="CopyToClipboard('tag9946');return false;" class="tag-decoration">testing-v5.1</div><div id="tag25360" onclick="CopyToClipboard('tag25360');return false;" class="tag-decoration">testing-v5.1.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/edc190356ebe08952bc00d0e0fa97177aec9163d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34418972124" target="_blank">2026-09-09 23:54:38</a></td></tr>
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
