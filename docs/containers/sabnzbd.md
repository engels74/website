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
<tr><td><div id="tag5504" onclick="CopyToClipboard('tag5504');return false;" class="tag-decoration">nightly</div><div id="tag12035" onclick="CopyToClipboard('tag12035');return false;" class="tag-decoration">nightly-bbe9bee</div><div id="tag19429" onclick="CopyToClipboard('tag19429');return false;" class="tag-decoration">nightly-cc61dc974b383e5bce04746274407448b6d0443e</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/bbe9beeea1a8b28bd80fd55590520175f213c462" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26710781459" target="_blank">2026-05-31 11:01:08</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag29306" onclick="CopyToClipboard('tag29306');return false;" class="tag-decoration">release</div><div id="tag8340" onclick="CopyToClipboard('tag8340');return false;" class="tag-decoration">release-bcf36ce</div><div id="tag14602" onclick="CopyToClipboard('tag14602');return false;" class="tag-decoration">release-5.0.3</div><div id="tag13121" onclick="CopyToClipboard('tag13121');return false;" class="tag-decoration">release-v5</div><div id="tag22355" onclick="CopyToClipboard('tag22355');return false;" class="tag-decoration">release-v5.0</div><div id="tag18839" onclick="CopyToClipboard('tag18839');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/bcf36cef7a746f9ef94e609755b9263b9a747688" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26710781564" target="_blank">2026-05-31 11:01:09</a></td></tr>
<tr><td><div id="tag2750" onclick="CopyToClipboard('tag2750');return false;" class="tag-decoration">testing</div><div id="tag31661" onclick="CopyToClipboard('tag31661');return false;" class="tag-decoration">testing-35e86b1</div><div id="tag26345" onclick="CopyToClipboard('tag26345');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag3212" onclick="CopyToClipboard('tag3212');return false;" class="tag-decoration">testing-v5</div><div id="tag5947" onclick="CopyToClipboard('tag5947');return false;" class="tag-decoration">testing-v5.0</div><div id="tag1907" onclick="CopyToClipboard('tag1907');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/35e86b1ac46e08f79c1335f266179e63eb9f2be5" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26680261806" target="_blank">2026-05-30 09:21:23</a></td></tr>
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
