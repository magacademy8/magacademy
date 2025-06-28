---
layout: home
title: "Hoş Geldiniz | Welcome"
lang: tr
---

# Merhaba!  
Bu sitede hizmetlerimi, portföyümü ve blog yazılarımı bulabilirsiniz.

---

# Hello!  
On this site, you can find my services, portfolio, and blog posts.

import React, { ReactNode, useState } from "react";

type LayoutProps = {
  children: ReactNode;
};

const Layout: React.FC<LayoutProps> = ({ children }) => {
  const [lang, setLang] = useState<"tr" | "en">("tr");

  const toggleLang = () => {
    setLang((prev) => (prev === "tr" ? "en" : "tr"));
  };

  return (
    <div style={{
      minHeight: "100vh",
      background: "linear-gradient(to right, #f8fafc, #e2e8f0)",
      fontFamily: "Inter, sans-serif"
    }}>
      <header style={{
        padding: "1.5rem 2rem",
        borderBottom: "1px solid #e5e7eb",
        background: "#ffffffdd",
        display: "flex",
        justifyContent: "space-between",
        alignItems: "center",
        boxShadow: "0 2px 8px 0 #e5e7eb"
      }}>
        <h1 style={{ margin: 0, fontSize: "1.6rem", letterSpacing: "2px", color: "#2563eb" }}>
          Meltem Portfolio
        </h1>
        <button
          onClick={toggleLang}
          style={{
            background: "#2563eb",
            color: "#fff",
            border: "none",
            borderRadius: "6px",
            padding: "0.6rem 1.2rem",
            fontWeight: "bold",
            cursor: "pointer",
            fontSize: "1rem",
            transition: "background 0.2s"
          }}
        >
          {lang === "tr" ? "English" : "Türkçe"}
        </button>
      </header>
      <main style={{
        maxWidth: "900px",
        margin: "2rem auto",
        background: "#fff",
        borderRadius: "12px",
        boxShadow: "0 4px 32px 0 #cbd5e1",
        padding: "2rem",
        minHeight: "60vh"
      }}>
        {children}
      </main>
      <footer style={{
        textAlign: "center",
        padding: "1rem",
        color: "#64748b",
        fontSize: "1rem"
      }}>
        © {new Date().getFullYear()} Meltem. All rights reserved.
      </footer>
    </div>
  );
};

export default Layout;
