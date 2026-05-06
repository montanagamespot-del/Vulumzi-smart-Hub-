# Vulumzi-smart-Hub-
This is any vulumzi ecosystem app builded by Montana 
import { useState } from "react"; import { Button } from "@/components/ui/button"; import { Card, CardContent } from "@/components/ui/card";

const symbols = [ "★", "☆", "✦", "✧", "✪", "✯", "✰", "☀", "☁", "☂", "☃", "⚡", "🔥", "❄", "❤", "♡", "✿", "✽", "✾", "❖", "☯", "∞", "▲", "▼", "◆", "◇", "●", "■" ];

export default function SymbolApp() { const [copied, setCopied] = useState(null);

const copySymbol = async (symbol) => { await navigator.clipboard.writeText(symbol); setCopied(symbol); setTimeout(() => setCopied(null), 1000); };

return ( <div className="min-h-screen bg-gray-100 p-6 flex flex-col items-center"> <h1 className="text-2xl font-bold mb-4">MJ Symbol Tester App</h1> <p className="text-gray-600 mb-6">Click a symbol to copy it</p>

<div className="grid grid-cols-5 gap-3 w-full max-w-md">
    {symbols.map((s, i) => (
      <Card
        key={i}
        className="cursor-pointer hover:scale-105 transition"
        onClick={() => copySymbol(s)}
      >
        <CardContent className="flex items-center justify-center p-4 text-2xl">
          {s}
        </CardContent>
      </Card>
    ))}
  </div>

  {copied && (
    <div className="mt-4 text-green-600 font-semibold">
      Copied: {copied}
    </div>
  )}

  <Button className="mt-6" onClick={() => setCopied("All symbols ready") }>
    Test App
  </Button>
</div>

); }
