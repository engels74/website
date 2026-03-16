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
<tr><td><div id="tag30156" onclick="CopyToClipboard('tag30156');return false;" class="tag-decoration">nightly</div><div id="tag20973" onclick="CopyToClipboard('tag20973');return false;" class="tag-decoration">nightly-f680479</div><div id="tag14148" onclick="CopyToClipboard('tag14148');return false;" class="tag-decoration">nightly-2c91e61d8ede7beda055deb1ec368295faee6846</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/f6804790167d1240219f6e88fe5a99a4168dc074" target="_blank">Version update: 934d81de91e1314fc794c873c6a1674d4c9ba4e8 => 2c91e61d8ede7beda055deb1ec368295faee6846</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/23151091586" target="_blank">2026-03-16 15:17:29</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag23587" onclick="CopyToClipboard('tag23587');return false;" class="tag-decoration">release</div><div id="tag22627" onclick="CopyToClipboard('tag22627');return false;" class="tag-decoration">release-33f5e7f</div><div id="tag30224" onclick="CopyToClipboard('tag30224');return false;" class="tag-decoration">release-4.5.5</div><div id="tag3331" onclick="CopyToClipboard('tag3331');return false;" class="tag-decoration">release-v4</div><div id="tag22215" onclick="CopyToClipboard('tag22215');return false;" class="tag-decoration">release-v4.5</div><div id="tag23630" onclick="CopyToClipboard('tag23630');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/33f5e7fdb3b3bca2cd7dbbb9774a5a7f05b0882d" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724225" target="_blank">2026-02-25 21:28:58</a></td></tr>
<tr><td><div id="tag25343" onclick="CopyToClipboard('tag25343');return false;" class="tag-decoration">testing</div><div id="tag24760" onclick="CopyToClipboard('tag24760');return false;" class="tag-decoration">testing-ea619d5</div><div id="tag28953" onclick="CopyToClipboard('tag28953');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag27879" onclick="CopyToClipboard('tag27879');return false;" class="tag-decoration">testing-v4</div><div id="tag5257" onclick="CopyToClipboard('tag5257');return false;" class="tag-decoration">testing-v4.5</div><div id="tag8835" onclick="CopyToClipboard('tag8835');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/ea619d52d293907d9b72038e1dff39f72d870f2e" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724984" target="_blank">2026-02-25 21:28:59</a></td></tr>
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
