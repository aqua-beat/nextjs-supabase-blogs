npx create-next-app@latest --example with-tailwindcss . --use-npm


/** @type {import('next').NextConfig} */
module.exports = {
  reactStrictMode: true,
  experimental: {
    appDir: true,
  },
}

npm i @supabase/auth-helpers-nextjs @supabase/supabase-js @types/uuid date-fns server-only sharp supabase uuid zustand
npm i -D encoding

npm run dev

Ctrl + C

// メインページ
const Page = () => {
  return (
    <div className="h-full">
      <div>メインページ</div>
    </div>
  )
}

export default Page


import '../styles/globals.css'
import Navigation from './components/navigation'

// レイアウト
const RootLayout = async ({ children }: { children: React.ReactNode }) => {
  return (
    <html>
      <body>
        <div className="flex flex-col min-h-screen">
          <Navigation />

          <main className="flex-1 container max-w-screen-xl mx-auto px-5 py-10">{children}</main>

          <footer className="py-5 border-t">
            <div className="text-center text-sm text-gray-500">
              Copyright © All rights reserved | PazuBlog
            </div>
          </footer>
        </div>
      </body>
    </html>
  )
}

export default RootLayout

#Navigation
'use client'

import Link from 'next/link'


const Navigation = () => {
  return (
    <header className="border-b py-5">
      <div className="container max-w-screen-xl mx-auto relative flex justify-center items-center">
        <Link href="/" className=" font-bold text-xl cursor-pointer">
          FullStackChannel
        </Link>

        <div className="absolute right-5">
          <div className="flex space-x-4">
            <Link href="/auth/profile">プロフィール</Link>
            <Link href="/auth/login">ログイン</Link>
            <Link href="/auth/signup">サインアップ</Link>
          </div>
        </div>
      </div>
    </header>
  )
}

export default Navigation


// ヘッダー
const Head = () => {
  return (
    <>
      <title>Blog</title>
      <meta content="width=device-width, initial-scale=1" name="viewport" />
      <meta name="description" content="Next.js Supabase Blog" />
      <link rel="icon" href="/favicon.ico" />
    </>
  )
}

export default Head

#確認
npm run dev
