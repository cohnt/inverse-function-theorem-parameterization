# Planning along Differentiable Charts of Constraint Manifolds with the Inverse Function Theorem

Project page for the paper by Thomas Cohn\*, Seiji Shaw\*, Harel Biggie, Travis Manderson,
Nicholas Roy, and Russ Tedrake (MIT CSAIL). \* denotes equal contribution.

Built on the [Academic Project Page Template](https://github.com/eliahuhorwitz/Academic-project-page-template).

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000/
```

There is no build step. `.nojekyll` is present so GitHub Pages serves `static/` verbatim.

## Structure

- `index.html` — the entire page.
- `static/css/`, `static/js/` — vendored Bulma, bulma-carousel, bulma-slider, Font Awesome, and the
  template's `index.css` / `index.js`. Academicons, MathJax, Inter, and jQuery load from CDNs.
- `static/images/` — figures, all derived from the paper source and the experiment repositories
  (see "Figure provenance" below).
- `static/videos/` — currently empty; the teaser loop goes here if one is added.

## TODO before publishing

The page is complete in structure but deliberately ships with placeholders. Each is marked with a
`TODO` comment in `index.html`.

1. **Venue.** The hero currently reads "Under review". Replace with the venue and year.
2. **Paper button.** Disabled. Remove the `coming-soon` class and set `href` to the PDF.
3. **arXiv button.** Disabled. Set `href` to `https://arxiv.org/abs/<ARXIV_ID>`.
4. **Code button.** Disabled. All three experiment repositories are currently **private**:
   - `cohnt/iiwa-bimanual-augmented-jacobian-test` (Experiment 1)
   - `cohnt/EAIK-IFT-Example` (Experiment 2)
   - `sageshoyu/rby1-constrained-planning` (Experiment 3)

   Make them public before linking. The URLs are already in a comment next to the button.
5. **Video button** and **the two YouTube embeds.** The overview video doubles as the teaser and sits
   directly under the hero; the hardware supplementary video sits in the RB-Y1 section. Upload both,
   then swap each `.media-placeholder` for the commented-out `<div class="publication-video">` block and
   fill in the video ID. Source files live in `rby1-constrained-planning/video/` as `overview_video.mp4`
   (named credits) and `ral_supplementary.mp4` (anonymous title card by default — regenerate with
   `make_cards.py --named` before uploading publicly).
6. **LinkedIn button.** Disabled until the announcement post exists.
7. **BibTeX.** Currently the literal text "TODO". Fill in once the venue and year are known.
8. **Social preview.** `static/images/social_preview.jpg` is an auto-generated 1200×630 crop of the
   teaser render; consider replacing it with a deliberately composed frame.

## Figure provenance

Derived at build time from read-only sources; regenerate with ImageMagick / `pdftoppm` / `ffmpeg`.

| File | Source |
| --- | --- |
| `teaser_rby1.jpg`, `social_preview.jpg` | `ift-ik-paper/media/rby1_swept_volume/sweep_p7_med.png` |
| `iiwa_swept_volume.jpg` | `ift-ik-paper/media/iiwa_swept_volume/swept_volume_225_cropped.png` |
| `grasp_selection.jpg` | `ift-ik-paper/media/grasp_selection.png` |
| `ur_scene.jpg` | `ift-ik-paper/media/ur_scene.png` |
| `autodiff_error.png`, `autodiff_runtime.png` | `ift-ik-paper/media/autodiff/*_cropped.pdf` |
| `rby1_grid_setup.png` | `rby1-constrained-planning/notebooks/box_placement_grid.png` |
| `rby1_grid_status.png` | `rby1-constrained-planning/plans/grid_cache/grid_status.png` |
| `domain_extension.gif` | `rby1-constrained-planning/video/v2_domain_extension.mp4` |
| `boundary_reach.gif` | `rby1-constrained-planning/video/v2_boundary_reach.mp4` |

## License

Website content is CC BY-SA 4.0 (see `LICENSE`). Vendored third-party assets keep their own licenses
(see `THIRD_PARTY.md`).
