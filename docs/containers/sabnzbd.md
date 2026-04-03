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
<tr><td><div id="tag17277" onclick="CopyToClipboard('tag17277');return false;" class="tag-decoration">nightly</div><div id="tag5034" onclick="CopyToClipboard('tag5034');return false;" class="tag-decoration">nightly-d829f58</div><div id="tag10597" onclick="CopyToClipboard('tag10597');return false;" class="tag-decoration">nightly-a587212c00b2403126636097721f04c7f4583fda</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/d829f587e2afd6389c0b709ed05d742b91e3d176" target="_blank">Version update: 998766e7f81ea061179776299ffe6ab7f0ab2eba => a587212c00b2403126636097721f04c7f4583fda</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/23939885513" target="_blank">2026-04-03 08:29:53</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag16893" onclick="CopyToClipboard('tag16893');return false;" class="tag-decoration">release</div><div id="tag19507" onclick="CopyToClipboard('tag19507');return false;" class="tag-decoration">release-33f5e7f</div><div id="tag7798" onclick="CopyToClipboard('tag7798');return false;" class="tag-decoration">release-4.5.5</div><div id="tag23037" onclick="CopyToClipboard('tag23037');return false;" class="tag-decoration">release-v4</div><div id="tag20770" onclick="CopyToClipboard('tag20770');return false;" class="tag-decoration">release-v4.5</div><div id="tag24514" onclick="CopyToClipboard('tag24514');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/33f5e7fdb3b3bca2cd7dbbb9774a5a7f05b0882d" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724225" target="_blank">2026-02-25 21:28:58</a></td></tr>
<tr><td><div id="tag32636" onclick="CopyToClipboard('tag32636');return false;" class="tag-decoration">testing</div><div id="tag25729" onclick="CopyToClipboard('tag25729');return false;" class="tag-decoration">testing-ea619d5</div><div id="tag13645" onclick="CopyToClipboard('tag13645');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag30653" onclick="CopyToClipboard('tag30653');return false;" class="tag-decoration">testing-v4</div><div id="tag476" onclick="CopyToClipboard('tag476');return false;" class="tag-decoration">testing-v4.5</div><div id="tag7766" onclick="CopyToClipboard('tag7766');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/ea619d52d293907d9b72038e1dff39f72d870f2e" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724984" target="_blank">2026-02-25 21:28:59</a></td></tr>
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
