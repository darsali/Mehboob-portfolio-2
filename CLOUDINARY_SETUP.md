# Cloudinary Setup Guide

Your portfolio has been configured to use Cloudinary for image storage. Follow these steps to complete the setup:

## Step 1: Get Cloudinary Account

1. Go to [Cloudinary.com](https://cloudinary.com) and sign up for a free account
2. After signing up, go to your Dashboard
3. Copy the following credentials from your Dashboard:
   - **Cloud Name**
   - **API Key** 
   - **API Secret**

## Step 2: Update Environment Variables

1. Open the `.env.local` file in your project root
2. Replace the placeholder values with your actual Cloudinary credentials:

```env
CLOUDINARY_CLOUD_NAME=your_actual_cloud_name
CLOUDINARY_API_KEY=your_actual_api_key
CLOUDINARY_API_SECRET=your_actual_api_secret
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME=your_actual_cloud_name
```

## Step 3: Upload Images to Cloudinary

Run the upload script to transfer all your images to Cloudinary:

```bash
npm run upload-images
```

This will:
- Upload all images from your `public/` folder to Cloudinary
- Create a `cloudinary-urls.json` file with URL mappings
- Display upload progress in the terminal

## Step 4: Verify the Setup

1. Start your development server: `npm run dev`
2. Open your website and check if all images are loading correctly
3. The images should now be served from Cloudinary CDN instead of your local server

## Benefits of Using Cloudinary

✅ **Faster Loading**: Images served from global CDN
✅ **Automatic Optimization**: Images automatically optimized for web
✅ **Responsive Images**: Automatic image resizing for different devices
✅ **Better Performance**: Reduced server load
✅ **Image Transformations**: On-the-fly image editing capabilities

## Troubleshooting

- **Images not loading**: Check if your environment variables are correct
- **Upload failed**: Verify your API credentials and internet connection
- **Build errors**: Make sure all environment variables are set

## File Structure

- `lib/cloudinary.ts` - Cloudinary configuration
- `lib/images.ts` - Image URL helper functions
- `scripts/upload-to-cloudinary.js` - Upload script
- `data/index.ts` - Updated to use Cloudinary URLs
- Components updated: `RecentProjects.tsx`, `Footer.tsx`, `InfiniteMovingCards.tsx`, `InfiniteCards.tsx`

Your portfolio is now ready to use Cloudinary for blazing-fast image delivery! 🚀