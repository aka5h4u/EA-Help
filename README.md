import { useState } from "react";
import { motion } from "framer-motion";
import { Card, CardContent } from "@/components/ui/card";
import { Input } from "@/components/ui/input";
import { Button } from "@/components/ui/button";
import { Search, User, HelpCircle, CreditCard, Plug, Code } from "lucide-react";

export default function EAStyleHelpDemo() {
  const [query, setQuery] = useState("");

  const articles = [
    { title: "Reset your password", tag: "Account" },
    { title: "Troubleshoot login issues", tag: "Account" },
    { title: "Configure payment gateway", tag: "Payments" },
    { title: "Refund processing steps", tag: "Payments" },
    { title: "Integration setup guide", tag: "Integrations" },
    { title: "API authentication", tag: "Developer" },
  ];

  const categories = [
    { title: "Account & Login", icon: User },
    { title: "Payments", icon: CreditCard },
    { title: "Integrations", icon: Plug },
    { title: "Developer APIs", icon: Code },
  ];

  const filtered = articles.filter((a) =>
    a.title.toLowerCase().includes(query.toLowerCase())
  );

  return (
    <div className="min-h-screen bg-slate-50 text-slate-900">
      {/* Header */}
      <header className="bg-slate-900 text-white">
        <div className="max-w-7xl mx-auto px-6 py-4 flex items-center justify-between gap-6">
          <div className="font-bold text-lg">Help Center Demo</div>

          <div className="hidden md:flex items-center gap-3 w-full max-w-md">
            <Search className="w-4 h-4" />
            <Input
              placeholder="Search help articles"
              className="bg-white text-black"
              value={query}
              onChange={(e) => setQuery(e.target.value)}
            />
          </div>

          <Button variant="secondary">Sign In</Button>
        </div>
      </header>

      {/* Hero Search */}
      <section className="bg-slate-800 text-white py-20">
        <div className="max-w-4xl mx-auto px-6 text-center">
          <motion.h1
            initial={{ opacity: 0, y: 20 }}
            animate={{ opacity: 1, y: 0 }}
            className="text-4xl md:text-5xl font-extrabold"
          >
            How can we help?
          </motion.h1>

          <p className="mt-4 text-slate-300">
            Search knowledge articles, guides, and troubleshooting topics
          </p>

          <div className="mt-8 flex gap-3 bg-white rounded-2xl p-3 shadow-lg">
            <Search className="w-5 h-5 mt-1 text-slate-500" />
            <input
              className="flex-1 outline-none text-black"
              placeholder="Search topics, features, errors"
              value={query}
              onChange={(e) => setQuery(e.target.value)}
            />
          </div>
        </div>
      </section>

      {/* Categories */}
      <section className="max-w-7xl mx-auto px-6 py-16">
        <h2 className="text-2xl font-bold">Browse by Category</h2>

        <div className="grid md:grid-cols-4 gap-6 mt-8">
          {categories.map((c) => (
            <motion.div key={c.title} whileHover={{ y: -6 }}>
              <Card className="rounded-2xl shadow-sm cursor-pointer">
                <CardContent className="p-6 flex flex-col items-center text-center gap-3">
                  <c.icon className="w-8 h-8" />
                  <div className="font-semibold">{c.title}</div>
                </CardContent>
              </Card>
            </motion.div>
          ))}
        </div>
      </section>

      {/* Articles */}
      <section className="max-w-5xl mx-auto px-6 py-10">
        <h2 className="text-2xl font-bold">Popular Articles</h2>

        <div className="mt-6 space-y-4">
          {filtered.map((a) => (
            <motion.div
              key={a.title}
              initial={{ opacity: 0, y: 10 }}
              animate={{ opacity: 1, y: 0 }}
            >
              <Card className="rounded-xl shadow-sm hover:shadow-md cursor-pointer">
                <CardContent className="p-5 flex items-center justify-between">
                  <div>
                    <div className="font-semibold">{a.title}</div>
                    <div className="text-xs mt-2 bg-slate-200 inline-block px-2 py-1 rounded-lg">
                      {a.tag}
                    </div>
                  </div>
                  <HelpCircle className="w-5 h-5" />
                </CardContent>
              </Card>
            </motion.div>
          ))}

          {filtered.length === 0 && (
            <div className="text-slate-500">No matching articles found.</div>
          )}
        </div>
      </section>

      {/* Support Panel */}
      <section className="max-w-4xl mx-auto px-6 py-16">
        <Card className="rounded-2xl shadow-sm">
          <CardContent className="p-10 text-center">
            <h3 className="text-xl font-bold">Still need help?</h3>
            <p className="text-slate-600 mt-3">
              Create a support case or start a live demo chat.
            </p>
            <div className="flex gap-4 justify-center mt-6">
              <Button>Open Case</Button>
              <Button variant="outline">Start Chat</Button>
            </div>
          </CardContent>
        </Card>
      </section>

      {/* Footer */}
      <footer className="bg-slate-900 text-slate-400 text-sm text-center py-8">
        Demo Help Center UI — Maantic
      </footer>
    </div>
  );
}
