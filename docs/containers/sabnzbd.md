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
<tr><td><div id="tag30283" onclick="CopyToClipboard('tag30283');return false;" class="tag-decoration">nightly</div><div id="tag15398" onclick="CopyToClipboard('tag15398');return false;" class="tag-decoration">nightly-92b44cf</div><div id="tag21897" onclick="CopyToClipboard('tag21897');return false;" class="tag-decoration">nightly-449157e0fb9d8996d3b4378efee2503e7475cdb4</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/92b44cfde9246d1c8146a4652f6755a8857eefa9" target="_blank">Version update: 89b3b97093390ec29cb89ec9fabeee25cb615dc2 => 449157e0fb9d8996d3b4378efee2503e7475cdb4</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/23318516416" target="_blank">2026-03-19 21:48:06</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag13785" onclick="CopyToClipboard('tag13785');return false;" class="tag-decoration">release</div><div id="tag17324" onclick="CopyToClipboard('tag17324');return false;" class="tag-decoration">release-33f5e7f</div><div id="tag7648" onclick="CopyToClipboard('tag7648');return false;" class="tag-decoration">release-4.5.5</div><div id="tag30239" onclick="CopyToClipboard('tag30239');return false;" class="tag-decoration">release-v4</div><div id="tag15821" onclick="CopyToClipboard('tag15821');return false;" class="tag-decoration">release-v4.5</div><div id="tag4677" onclick="CopyToClipboard('tag4677');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/33f5e7fdb3b3bca2cd7dbbb9774a5a7f05b0882d" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724225" target="_blank">2026-02-25 21:28:58</a></td></tr>
<tr><td><div id="tag29307" onclick="CopyToClipboard('tag29307');return false;" class="tag-decoration">testing</div><div id="tag7091" onclick="CopyToClipboard('tag7091');return false;" class="tag-decoration">testing-ea619d5</div><div id="tag20327" onclick="CopyToClipboard('tag20327');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag16428" onclick="CopyToClipboard('tag16428');return false;" class="tag-decoration">testing-v4</div><div id="tag1928" onclick="CopyToClipboard('tag1928');return false;" class="tag-decoration">testing-v4.5</div><div id="tag21370" onclick="CopyToClipboard('tag21370');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/ea619d52d293907d9b72038e1dff39f72d870f2e" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724984" target="_blank">2026-02-25 21:28:59</a></td></tr>
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
