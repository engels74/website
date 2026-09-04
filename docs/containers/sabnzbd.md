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
<tr><td><div id="tag830" onclick="CopyToClipboard('tag830');return false;" class="tag-decoration">nightly</div><div id="tag28034" onclick="CopyToClipboard('tag28034');return false;" class="tag-decoration">nightly-2b18b76</div><div id="tag26346" onclick="CopyToClipboard('tag26346');return false;" class="tag-decoration">nightly-d25d857fc4c6d1d7c7bf9fffb718074d50cda325</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/2b18b763eccb9bd5a186307b33531bc1400d6a12" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33877198193" target="_blank">2026-09-04 13:16:57</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag12516" onclick="CopyToClipboard('tag12516');return false;" class="tag-decoration">release</div><div id="tag14394" onclick="CopyToClipboard('tag14394');return false;" class="tag-decoration">release-5da462e</div><div id="tag20576" onclick="CopyToClipboard('tag20576');return false;" class="tag-decoration">release-5.1.2</div><div id="tag5212" onclick="CopyToClipboard('tag5212');return false;" class="tag-decoration">release-v5</div><div id="tag31889" onclick="CopyToClipboard('tag31889');return false;" class="tag-decoration">release-v5.1</div><div id="tag26099" onclick="CopyToClipboard('tag26099');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5da462ec75174d481f861cdd3b553e78d3f6237c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33803892915" target="_blank">2026-09-03 20:43:08</a></td></tr>
<tr><td><div id="tag29355" onclick="CopyToClipboard('tag29355');return false;" class="tag-decoration">testing</div><div id="tag7183" onclick="CopyToClipboard('tag7183');return false;" class="tag-decoration">testing-2a1223c</div><div id="tag5707" onclick="CopyToClipboard('tag5707');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag27574" onclick="CopyToClipboard('tag27574');return false;" class="tag-decoration">testing-v5</div><div id="tag3716" onclick="CopyToClipboard('tag3716');return false;" class="tag-decoration">testing-v5.1</div><div id="tag8946" onclick="CopyToClipboard('tag8946');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2a1223cbcb89b0795d40299cbd8efd5e4549fa8f" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33916522917" target="_blank">2026-09-04 20:29:59</a></td></tr>
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
