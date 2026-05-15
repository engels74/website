---
hide:
  - toc
title: engels74/qflood
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/qflood){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/qflood){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Upstream Project](https://github.com/jesec/flood){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="/img/image-logos/qflood.svg" alt="logo"></div>

!!! question "What is this?"

    This is a fork of Hotio's [rflood](https://hotio.dev/containers/rflood) Docker image, that uses qBittorrent instead of rtorrent. The qflood image has both "releases" and "nightly support". The included [qBittorrent](https://github.com/userdocs/qbittorrent-nox-static) uses libtorrent v2.x.

???+ info "What is nightly?"

    Nightly means it updates automatically after a successful run of [this workflow file](https://github.com/jesec/flood/actions/workflows/publish-rolling.yml). This means that whenever the official flood repository receives a push commit, this docker image should automatically be updated. All thanks to hotio's brilliant setup.

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
<tr><td><div id="tag10143" onclick="CopyToClipboard('tag10143');return false;" class="tag-decoration">nightly</div><div id="tag10565" onclick="CopyToClipboard('tag10565');return false;" class="tag-decoration">nightly-7dd7df3</div><div id="tag4986" onclick="CopyToClipboard('tag4986');return false;" class="tag-decoration">nightly-5.2.0--25919415228</div><div id="tag15469" onclick="CopyToClipboard('tag15469');return false;" class="tag-decoration">nightly-v5</div><div id="tag19085" onclick="CopyToClipboard('tag19085');return false;" class="tag-decoration">nightly-v5.2</div><div id="tag26840" onclick="CopyToClipboard('tag26840');return false;" class="tag-decoration">nightly-v5.2.0</div></td><td>nightly</td><td><a href="https://github.com/engels74/qflood/commit/7dd7df3f40b010f658bfdf00c13351a6e2705572" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/qflood/actions/runs/25923349375" target="_blank">2026-05-15 14:29:49</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag30069" onclick="CopyToClipboard('tag30069');return false;" class="tag-decoration">release</div><div id="tag10779" onclick="CopyToClipboard('tag10779');return false;" class="tag-decoration">release-d900853</div><div id="tag25446" onclick="CopyToClipboard('tag25446');return false;" class="tag-decoration">release-5.2.0--4.14.1</div><div id="tag18983" onclick="CopyToClipboard('tag18983');return false;" class="tag-decoration">release-v5</div><div id="tag23536" onclick="CopyToClipboard('tag23536');return false;" class="tag-decoration">release-v5.2</div><div id="tag11738" onclick="CopyToClipboard('tag11738');return false;" class="tag-decoration">release-v5.2.0</div></td><td>Releases</td><td><a href="https://github.com/engels74/qflood/commit/d90085349ff0f0c434ef49d1e488ba01bdb0ab72" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/qflood/actions/runs/25918947767" target="_blank">2026-05-15 12:55:38</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name qflood \
        -p 8080:8080 \
        -p 3000:3000 \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e TZ="Etc/UTC" \
        -e LIBTORRENT="v2" \
        -e FLOOD_AUTH="true" \
        -e ARGS="" \
        -e FLOOD_ARGS="" \
        -v /<host_folder_config>:/config \
        -v /<host_folder_data>:/data \
        ghcr.io/engels74/qflood
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      qflood:
        container_name: qflood
        image: ghcr.io/engels74/qflood
        ports:
          - "8080:8080"
          - "3000:3000"
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
          - LIBTORRENT=v2
          - FLOOD_AUTH=true
          - ARGS
          - FLOOD_ARGS
        volumes:
          - /<host_folder_config>:/config
          - /<host_folder_data>:/data
    ```

## Changing the WebUI port

Under certain circumstances it's required to run the WebUI on a different internal port, you can do that by modifying the environment variable `WEBUI_PORTS` accordingly. It should be in the format `xxxx/tcp,xxxx/udp`, take a look at the default with `docker logs` (variable is printed at container start) or `docker inspect`.

--8<-- "includes/wireguard.md"
