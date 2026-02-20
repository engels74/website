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
<tr><td><div id="tag5189" onclick="CopyToClipboard('tag5189');return false;" class="tag-decoration">nightly</div><div id="tag29170" onclick="CopyToClipboard('tag29170');return false;" class="tag-decoration">nightly-67756ac</div><div id="tag26392" onclick="CopyToClipboard('tag26392');return false;" class="tag-decoration">nightly-9b1b503ce6f2b70df39d2296aed4b7e296f2f18f</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/67756ac1342ebafabedb3a34ed064a9a29adbf5f" target="_blank">Version update: bc4c4bbcfaaadfc09ef2bddfe3f95b17c0214c1b => 9b1b503ce6f2b70df39d2296aed4b7e296f2f18f</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22219031912" target="_blank">2026-02-20 09:39:59</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag13169" onclick="CopyToClipboard('tag13169');return false;" class="tag-decoration">release</div><div id="tag23175" onclick="CopyToClipboard('tag23175');return false;" class="tag-decoration">release-252442e</div><div id="tag3279" onclick="CopyToClipboard('tag3279');return false;" class="tag-decoration">release-4.5.5</div><div id="tag4746" onclick="CopyToClipboard('tag4746');return false;" class="tag-decoration">release-v4</div><div id="tag4104" onclick="CopyToClipboard('tag4104');return false;" class="tag-decoration">release-v4.5</div><div id="tag20066" onclick="CopyToClipboard('tag20066');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/252442ee081e7bffb07db68d74238fe65fe61492" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823272944" target="_blank">2026-02-09 11:29:10</a></td></tr>
<tr><td><div id="tag6247" onclick="CopyToClipboard('tag6247');return false;" class="tag-decoration">testing</div><div id="tag3697" onclick="CopyToClipboard('tag3697');return false;" class="tag-decoration">testing-3dc0cdf</div><div id="tag13997" onclick="CopyToClipboard('tag13997');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag10975" onclick="CopyToClipboard('tag10975');return false;" class="tag-decoration">testing-v4</div><div id="tag21560" onclick="CopyToClipboard('tag21560');return false;" class="tag-decoration">testing-v4.5</div><div id="tag6967" onclick="CopyToClipboard('tag6967');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3dc0cdf9be0128f86ab1d3137f11ee412fbc5fa6" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823273556" target="_blank">2026-02-09 11:29:12</a></td></tr>
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
