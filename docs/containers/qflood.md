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
<tr><td><div id="tag11563" onclick="CopyToClipboard('tag11563');return false;" class="tag-decoration">nightly</div><div id="tag13615" onclick="CopyToClipboard('tag13615');return false;" class="tag-decoration">nightly-45c031f</div><div id="tag12031" onclick="CopyToClipboard('tag12031');return false;" class="tag-decoration">nightly-5.1.4--22806479038</div><div id="tag24039" onclick="CopyToClipboard('tag24039');return false;" class="tag-decoration">nightly-v5</div><div id="tag24372" onclick="CopyToClipboard('tag24372');return false;" class="tag-decoration">nightly-v5.1</div><div id="tag5892" onclick="CopyToClipboard('tag5892');return false;" class="tag-decoration">nightly-v5.1.4</div></td><td>nightly</td><td><a href="https://github.com/engels74/qflood/commit/45c031f2d66d9c61bf48b6b5699645c9cb77fecd" target="_blank">Version update: 5.1.4--22806294120 => 5.1.4--22806479038</a></td><td><a href="https://github.com/engels74/qflood/actions/runs/22806906431" target="_blank">2026-03-07 20:45:32</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag23826" onclick="CopyToClipboard('tag23826');return false;" class="tag-decoration">release</div><div id="tag19141" onclick="CopyToClipboard('tag19141');return false;" class="tag-decoration">release-90b97ec</div><div id="tag8156" onclick="CopyToClipboard('tag8156');return false;" class="tag-decoration">release-5.1.4--4.13.0</div><div id="tag25637" onclick="CopyToClipboard('tag25637');return false;" class="tag-decoration">release-v5</div><div id="tag21802" onclick="CopyToClipboard('tag21802');return false;" class="tag-decoration">release-v5.1</div><div id="tag15842" onclick="CopyToClipboard('tag15842');return false;" class="tag-decoration">release-v5.1.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/qflood/commit/90b97ec099ccec6d001fd92e07245b3c4c461744" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/qflood/actions/runs/22416723001" target="_blank">2026-02-25 21:28:55</a></td></tr>
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
