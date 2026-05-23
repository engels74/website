---
hide:
  - toc
title: engels74/overseerr-anime
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/overseerr-anime){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/overseerr-anime){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Maintained Replacement](https://github.com/seerr-team/seerr){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="https://i.imgur.com/BcvImhI.png" alt="logo"></div>

!!! danger "Deprecated — do not use for new installs"

    **`engels74/overseerr-anime` is deprecated and will not receive further updates.**
    It is based on an old Overseerr anime-instance pull request and may contain
    unfixed CVEs inherited from the old Overseerr dependency stack.

    Existing users should plan to migrate away from this image. Upstream
    Overseerr and Jellyseerr have merged into the maintained
    [Seerr](https://github.com/seerr-team/seerr){ target="_blank" rel="noopener" }
    project, and new installs should use Seerr instead.

??? info "Read more: known CVE context"

    The final v1.34.0-era Overseerr Anime build contains `axios` 1.3.4. GitHub
    advisory
    [GHSA-fvcv-3m26-pcqx](https://github.com/axios/axios/security/advisories/GHSA-fvcv-3m26-pcqx){ target="_blank" rel="noopener" }
    tracks **CVE-2026-40175**, an Unrestricted Cloud Metadata Exfiltration
    vulnerability via a header injection chain. The advisory lists axios
    `>=1.0.0` as vulnerable and `>=1.15.0` as patched. This is separate from the
    axios package hijack incident.

    Seerr patched this in
    [v3.1.1](https://github.com/seerr-team/seerr/releases/tag/v3.1.1){ target="_blank" rel="noopener" }
    or later. The v3.1.1 release was published on 2026-04-13. This Docker image
    will not receive that dependency update.

!!! question "What is this?"

    This was a fork of Hotio's [overseerr](https://hotio.dev/containers/overseerr){ target="_blank" rel="noopener" }
    Docker image that bundled the historical
    [Anime Instance PR (#3664)](https://github.com/sct/overseerr/pull/3664){ target="_blank" rel="noopener" }.

    It was built using [this fork of the PR](https://github.com/engels74/overseerr-anime-source){ target="_blank" rel="noopener" }.
    This page is kept for existing users who need to identify what they are
    running; it is not a recommendation to deploy the image.

!!! note "Migration and alternatives"

    There is no exact drop-in replacement for this image today.

    - **Recommended path:** migrate to the official
      [Seerr](https://github.com/seerr-team/seerr){ target="_blank" rel="noopener" }
      image and follow the
      [Seerr migration guide](https://docs.seerr.dev/migration-guide/){ target="_blank" rel="noopener" }.
    - **Closest workaround:** [Redirecterr](https://github.com/varthe/Redirecterr){ target="_blank" rel="noopener" }
      can route requests to different Sonarr/Radarr instances, but it is
      webhook-driven and can conflict with any existing Seerr/Overseerr webhook
      workflow.
    - **Future built-in option:** Seerr PR
      [#2452](https://github.com/seerr-team/seerr/pull/2452){ target="_blank" rel="noopener" }
      is intended to add routing-rule behavior. As of 2026-05-20, it is still
      open as a draft and has not been merged.

!!! note "Branches and Tags"

    This project is no longer actively maintained.

    - **`:release` (or `:latest`)**:
      Final archived build from the
      [`feature-default-anime-instance-checkbox-release`](https://github.com/engels74/overseerr-anime-source/tree/feature-default-anime-instance-checkbox-release){ target="_blank" rel="noopener" }
      branch. No future security or dependency updates are planned.

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
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag22103" onclick="CopyToClipboard('tag22103');return false;" class="tag-decoration">release</div><div id="tag11297" onclick="CopyToClipboard('tag11297');return false;" class="tag-decoration">release-16f1fb0</div><div id="tag24463" onclick="CopyToClipboard('tag24463');return false;" class="tag-decoration">release-9c4845f982d922c2ebc18d9318cb56746006b19d</div></td><td>Releases</td><td><a href="https://github.com/engels74/overseerr-anime/commit/16f1fb0235fa08edafa521129cd1e8dc8a37131a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/overseerr-anime/actions/runs/26318966162" target="_blank">2026-05-23 00:51:09</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

!!! warning "Existing deployments only"

    The examples below are retained for existing users who need to identify or
    temporarily reproduce their current deployment. Do not use this image for new
    installs; use [Seerr](https://github.com/seerr-team/seerr){ target="_blank" rel="noopener" } instead.

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name overseerr-anime \
        -p 5055:5055 \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e TZ="Etc/UTC" \
        -e WEBUI_PORTS="5055/tcp,5055/udp" \
        -v /<host_folder_config>:/config \
        ghcr.io/engels74/overseerr-anime
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      overseerr-anime:
        container_name: overseerr-anime
        image: ghcr.io/engels74/overseerr-anime
        ports:
          - "5055:5055"
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
          - WEBUI_PORTS=5055/tcp,5055/udp
        volumes:
          - /<host_folder_config>:/config
    ```

--8<-- "includes/wireguard.md"
