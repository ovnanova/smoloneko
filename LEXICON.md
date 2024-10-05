# 📖 Lexicon

- `e`: The main div element representing oneko
- `s`: Object containing sprite positions for different states and directions
- `p`: Function to set the background position (sprite) of oneko
- `x`: Current x-position of oneko
- `y`: Current y-position of oneko
- `m`: Current x-position of the mouse cursor
- `v`: Current y-position of the mouse cursor
- `f`: Frame count for animation
- `i`: Idle time counter
- `a`: Current animation state
- `r`: Frame counter for the current animation
- `w`: Window inner width
- `h`: Window inner height
- `T`: Timestamp of the last frame
- `S`: Speed of oneko's movement
- `st`: Current state of oneko ("i", "a", or "c")
- `af`: Frame counter for the alert state
- `n`: Temporary variable for x-distance between oneko and cursor
- `c`: Temporary variable for y-distance between oneko and cursor
- `d`: Distance between oneko and cursor
- `g`: Temporary variable for determining oneko's direction
- `l`: Function to handle idle animations
- `u`: Main animation loop function

## Sprite States

- `i`: Idle
- `a`: Alert
- `s1`: Scratch self
- `s2`: Scratch wall top (only at top boundary)
- `s3`: Scratch wall bottom (only at bottom boundary)
- `s4`: Scratch wall right (only at right boundary)
- `s5`: Scratch wall left (only at left boundary)
- `t`: Tired
- `z`: Sleeping

## Main States

- `i`: Idle state
- `a`: Alert state
- `c`: Chase state

## Functions

- `p(n, f)`: Sets the sprite for oneko based on the state `n` and frame `f`
- `l()`: Handles idle animations and state changes during idle time
- `u(t)`: Main animation loop, handling state transitions and movement

## Behavior

1. oneko starts in the idle state at the top-left corner of the window.
2. When the mouse moves, oneko enters the alert state for 6 frames.
3. After the alert state, oneko chases the cursor.
4. oneko returns to idle state when:
   - It gets within 42 pixels of the cursor
   - It reaches any window boundary
5. During idle state, oneko may perform random animations:
   - Sleeping (with a tired transition)
   - Self scratching
   - Wall scratching (only when exactly at a window boundary)
6. Wall scratching animations are only triggered when oneko is exactly at the corresponding window boundary:
   - Left boundary (x == 16): left wall scratch
   - Top boundary (y == 16): top wall scratch
   - Right boundary (x == window width - 16): right wall scratch
   - Bottom boundary (y == window height - 16): bottom wall scratch
