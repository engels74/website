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
<tr><td><div id="tag31967" onclick="CopyToClipboard('tag31967');return false;" class="tag-decoration">nightly</div><div id="tag23458" onclick="CopyToClipboard('tag23458');return false;" class="tag-decoration">nightly-2aac18b</div><div id="tag23290" onclick="CopyToClipboard('tag23290');return false;" class="tag-decoration">nightly-7cd04f22f28900323a825929ab0c42959b9dca87</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/2aac18b0706671d9696b0e4dc04738d976a7d6ce" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/35768336769" target="_blank">2026-09-22 18:36:52</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag7214" onclick="CopyToClipboard('tag7214');return false;" class="tag-decoration">release</div><div id="tag18716" onclick="CopyToClipboard('tag18716');return false;" class="tag-decoration">release-7f49c81</div><div id="tag29943" onclick="CopyToClipboard('tag29943');return false;" class="tag-decoration">release-5.1.3</div><div id="tag32067" onclick="CopyToClipboard('tag32067');return false;" class="tag-decoration">release-v5</div><div id="tag8861" onclick="CopyToClipboard('tag8861');return false;" class="tag-decoration">release-v5.1</div><div id="tag22865" onclick="CopyToClipboard('tag22865');return false;" class="tag-decoration">release-v5.1.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7f49c8193cfd6e4bfb7d1d5f6ec8325d3ab09c27" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34482526229" target="_blank">2026-09-10 13:25:12</a></td></tr>
<tr><td><div id="tag14412" onclick="CopyToClipboard('tag14412');return false;" class="tag-decoration">testing</div><div id="tag17645" onclick="CopyToClipboard('tag17645');return false;" class="tag-decoration">testing-ffe78cf</div><div id="tag230" onclick="CopyToClipboard('tag230');return false;" class="tag-decoration">testing-5.1.3</div><div id="tag3580" onclick="CopyToClipboard('tag3580');return false;" class="tag-decoration">testing-v5</div><div id="tag11690" onclick="CopyToClipboard('tag11690');return false;" class="tag-decoration">testing-v5.1</div><div id="tag5548" onclick="CopyToClipboard('tag5548');return false;" class="tag-decoration">testing-v5.1.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/ffe78cf751803bd92188cb006e353d499184f818" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34482510601" target="_blank">2026-09-10 13:25:03</a></td></tr>
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
