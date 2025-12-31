# Nihao
/pages/index.js
import Head from "next/head";
import { motion } from "framer-motion";
import { useTranslation } from "react-i18next";
import { useState } from "react";
import "../i18n";

/* ---------------- iOS 风格动态背景 ---------------- */
function IOSBackground() {
  return (
    <div className="absolute inset-0 overflow-hidden -z-10">
      <div className="absolute inset-0 bg-gradient-to-br from-slate-900 via-indigo-900 to-black" />

      <motion.div
        className="absolute w-[600px] h-[600px] rounded-full 
        bg-gradient-to-tr from-blue-500/40 to-cyan-300/20 blur-3xl"
        animate={{ x: [0, 120, -80, 0], y: [0, -100, 80, 0] }}
        transition={{ duration: 30, repeat: Infinity, ease: "easeInOut" }}
        style={{ top: "10%", left: "10%" }}
      />

      <motion.div
        className="absolute w-[500px] h-[500px] rounded-full 
        bg-gradient-to-tr from-purple-500/30 to-pink-400/20 blur-3xl"
        animate={{ x: [0, -120, 100, 0], y: [0, 120, -120, 0] }}
        transition={{ duration: 36, repeat: Infinity, ease: "easeInOut" }}
        style={{ bottom: "10%", right: "5%" }}
      />

      <div className="absolute inset-0 backdrop-blur-[60px] bg-white/5" />
    </div>
  );
}

/* ---------------- 时间轴数据 ---------------- */
const timeline = [
  {
    title: "Geological Era",
    text: "Formed through geological processes over hundreds of millions of years."
  },
  {
    title: "Pre-Qin – Han",
    text: "Mount Tai became a symbolic axis between heaven and earth."
  },
  {
    title: "Tang – Song",
    text: "Developed into a cultural and artistic symbol."
  },
  {
    title: "Ming – Qing",
    text: "Widely used in gardens, studios, and scholarly spaces."
  },
  {
    title: "Modern Era",
    text: "Reinterpreted as a medium connecting nature, space, and design."
  }
];

/* ---------------- 首页 ---------------- */
export default function Home() {
  const { t, i18n } = useTranslation();
  const [lang, setLang] = useState(i18n.language || "en");

  const toggleLang = () => {
    const next = lang === "en" ? "zh" : "en";
    i18n.changeLanguage(next);
    setLang(next);
  };

  return (
    <>
      <Head>
        <title>泰山石 | Taishan Stone — Cultural Symbol of Stability</title>
        <meta
          name="description"
          content="泰山石源自五岳之首泰山，是象征稳定、秩序与文化精神的自然之石。探索泰山石的历史、文化与当代表达。"
        />
        <meta
          name="keywords"
          content="Taishan Stone, Mount Tai, Chinese culture, stone art, museum design"
        />
        <meta property="og:title" content="Taishan Stone" />
        <meta
          property="og:description"
          content="A cultural symbol of stability, order, and harmony inspired by Mount Tai."
        />
      </Head>

      <main className="relative min-h-screen text-white overflow-hidden">
        <IOSBackground />

        {/* 顶部 */}
        <header className="max-w-7xl mx-auto px-8 pt-10 flex justify-between items-center">
          <h1 className="text-3xl md:text-4xl font-bold tracking-wide">
            泰山石
          </h1>
          <button
            onClick={toggleLang}
            className="bg-white/20 backdrop-blur px-4 py-2 rounded-lg hover:bg-white/30"
          >
            {lang === "en" ? "中文" : "English"}
          </button>
        </header>

        {/* Hero */}
        <section className="max-w-5xl mx-auto text-center mt-24 px-6">
          <motion.h2
            initial={{ opacity: 0, y: 30 }}
            animate={{ opacity: 1, y: 0 }}
            transition={{ duration: 0.8 }}
            className="text-5xl font-bold mb-6"
          >
            泰山石 · 五岳之尊
          </motion.h2>

          <p className="text-xl text-gray-200 max-w-3xl mx-auto">
            Taishan Stone — A Cultural Symbol of Stability, Order, and Nature
          </p>
        </section>

        {/* 博物馆级介绍 */}
        <section className="max-w-6xl mx-auto mt-28 px-6">
          <div className="bg-white/10 backdrop-blur-xl rounded-2xl p-10 border border-white/20">
            <h3 className="text-3xl font-semibold mb-6">泰山石介绍</h3>

            <p className="text-gray-200 leading-relaxed mb-4">
              泰山，居五岳之首，自古被视为天地交汇之地。其山势雄浑、岩体古老，
              是中华文明中“稳定”“秩序”与“根基”的象征。
            </p>

            <p className="text-gray-200 leading-relaxed mb-4">
              泰山石源于这一自然体系，承载着地质演化的时间痕迹，
              也凝结着东方文化中对山岳精神的理解。
            </p>

            <p className="text-gray-200 leading-relaxed">
              今日，泰山石作为文化载体，被重新诠释为连接自然、时间与空间秩序的艺术存在。
            </p>
          </div>
        </section>

        {/* 作用 + 摆放 */}
        <section className="max-w-6xl mx-auto mt-20 px-6 grid md:grid-cols-2 gap-10">
          <motion.div
            whileHover={{ y: -6 }}
            className="bg-white/10 backdrop-blur-xl rounded-2xl p-8 border border-white/20"
          >
            <h3 className="text-2xl font-semibold mb-4">文化与空间价值</h3>
            <ul className="list-disc list-inside space-y-2 text-gray-200">
              <li>象征稳定、秩序与结构之美</li>
              <li>体现东方自然观与山岳文化</li>
              <li>强化空间的精神重心</li>
              <li>自然材料与艺术表达的结合</li>
              <li>适合收藏、展示与空间设计</li>
            </ul>
          </motion.div>

          <motion.div
            whileHover={{ y: -6 }}
            className="bg-white/10 backdrop-blur-xl rounded-2xl p-8 border border-white/20"
          >
            <h3 className="text-2xl font-semibold mb-4">摆放位置建议</h3>
            <ul className="list-disc list-inside space-y-2 text-gray-200">
              <li>空间主视觉或中轴位置</li>
              <li>入口或过渡区域</li>
              <li>书房 / 工作空间</li>
              <li>展示柜或陈列台</li>
              <li>庭院与半开放空间</li>
            </ul>
          </motion.div>
        </section>

        {/* 时间轴 */}
        <section className="max-w-5xl mx-auto mt-28 px-6">
          <h2 className="text-4xl font-bold text-center mb-14">
            泰山石文化时间轴
          </h2>

          <div className="border-l border-white/20 pl-8 space-y-10">
            {timeline.map((item, i) => (
              <div key={i} className="relative">
                <span className="absolute -left-[10px] top-1 w-4 h-4 bg-white rounded-full" />
                <h3 className="text-xl font-semibold">{item.title}</h3>
                <p className="text-gray-300 mt-2">{item.text}</p>
              </div>
            ))}
          </div>
        </section>

        {/* Footer */}
        <footer className="mt-32 py-12 text-center text-gray-400">
          <p>© Taishan Stone · Cultural Archive & Design</p>
        </footer>
      </main>
    </>
  );
}
