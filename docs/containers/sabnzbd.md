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
<tr><td><div id="tag10939" onclick="CopyToClipboard('tag10939');return false;" class="tag-decoration">nightly</div><div id="tag3488" onclick="CopyToClipboard('tag3488');return false;" class="tag-decoration">nightly-d7eb766</div><div id="tag17807" onclick="CopyToClipboard('tag17807');return false;" class="tag-decoration">nightly-2f4750f77d053665b50556f82852d5cb791a1737</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/d7eb7661f85a25b74a2633b7ee24b3933fa00d7a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26312390131" target="_blank">2026-05-22 21:16:51</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag15091" onclick="CopyToClipboard('tag15091');return false;" class="tag-decoration">release</div><div id="tag19667" onclick="CopyToClipboard('tag19667');return false;" class="tag-decoration">release-70d8e60</div><div id="tag3093" onclick="CopyToClipboard('tag3093');return false;" class="tag-decoration">release-5.0.3</div><div id="tag18963" onclick="CopyToClipboard('tag18963');return false;" class="tag-decoration">release-v5</div><div id="tag12787" onclick="CopyToClipboard('tag12787');return false;" class="tag-decoration">release-v5.0</div><div id="tag23706" onclick="CopyToClipboard('tag23706');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/70d8e606c26349a1a1d3680daa07fb14e8908e3a" target="_blank">Modified: meta.json, packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26287574256" target="_blank">2026-05-22 12:24:03</a></td></tr>
<tr><td><div id="tag31255" onclick="CopyToClipboard('tag31255');return false;" class="tag-decoration">testing</div><div id="tag26104" onclick="CopyToClipboard('tag26104');return false;" class="tag-decoration">testing-8806b84</div><div id="tag14373" onclick="CopyToClipboard('tag14373');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag6124" onclick="CopyToClipboard('tag6124');return false;" class="tag-decoration">testing-v5</div><div id="tag19873" onclick="CopyToClipboard('tag19873');return false;" class="tag-decoration">testing-v5.0</div><div id="tag30112" onclick="CopyToClipboard('tag30112');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8806b84f19af7e435040ffbdf575cca033b71bd1" target="_blank">Modified: meta.json, packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26287572564" target="_blank">2026-05-22 12:24:01</a></td></tr>
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
