PDF Size Compressor

A professional-grade, client-side PDF optimization tool that allows users to target specific file sizes. Built with privacy and performance in mind, all processing occurs locally in the user's browser—no files are ever uploaded to a server.

🚀 Key Features

Target Size Compression: Specify exactly how many KB or MB you want the final file to be.

Percentage-Based Reduction: Quickly scale down file size using a relative slider.

Smart Auto Optimization: Lossless cleanup of metadata and internal structural bloat.

No File Size Limits: Handles large PDFs by utilizing local device resources.

Privacy First: Files never leave the local machine, ensuring 100% data security.

Fully Responsive: Optimized for desktop, tablet, and mobile browsers.

🛠 Recent Updates & Bug Fixes

1. Readability & UI

Enhanced Contrast: Switched to a high-contrast color palette (--text-main: #0f172a) to ensure text is sharp and legible against the background.

Visual Feedback: Added dynamic info boxes that warn users about processing times for large files and potential quality loss for aggressive compression targets.

2. Responsive Design

Fluid Layouts: Implemented flexible flexbox wrapping and CSS media queries. The tool now stacks input groups vertically on mobile devices to prevent horizontal scrolling and UI breaking.

Touch Optimization: Increased tap targets and adjusted padding for better usability on touchscreens.

3. Unlimited File Support

Removed Restrictions: Hardcoded file size limits (previously 50MB) have been removed.

Device-Aware UI: Added a warning notification that appears automatically when files over 20MB are uploaded, informing the user that performance depends on their local hardware.

4. MB Compression Bug Fix

The Issue: Previously, selecting "MB" often resulted in "KB" sized files because the internal rendering engine was capped at a low resolution.

The Fix: * Increased maximum render scale from 1.5x to 4.0x.

Implemented a Binary Search Quality Algorithm that intelligently hones in on the target byte count by adjusting JPEG quality and resolution iteratively.

Added a Canvas Max Area Safety Guard to prevent browser crashes on mobile devices by capping the maximum pixel area while maintaining the highest possible quality within that limit.

📋 Technical Stack

pdf-lib: Used for structural manipulation, metadata stripping, and final PDF assembly.

pdf.js: Used as the core rendering engine to rasterize PDF pages for high-ratio lossy compression.

Vanilla JS/CSS3: Ensures lightweight performance without the overhead of heavy frameworks.

💡 How It Works (Lossy Compression Logic)

Rendering: The tool renders each PDF page onto an invisible HTML5 Canvas.

Scale Adjustment: It calculates a "byte budget" per page. If the budget is high (e.g., targeting 5MB), it renders at a higher DPI.

Binary Search: It performs multiple "test renders" of the JPEG data at different quality levels to find the exact point where the file size meets the user's request without losing more quality than necessary.

Re-assembly: The optimized images are wrapped back into a fresh PDF structure using pdf-lib.

📄 License

This tool is provided for web development use and can be integrated into existing web toolkits.
