import { motion } from "framer-motion";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Github, Linkedin, Mail, Database, Cloud, Code, Cpu } from "lucide-react";

export default function Portfolio() {
  const techStacks = [
    { name: "React", icon: Code },
    { name: "Node.js", icon: Cpu },
    { name: "PostgreSQL", icon: Database },
    { name: "AWS", icon: Cloud },
  ];

  return (
    <div className="min-h-screen bg-cover bg-center bg-no-repeat flex flex-col items-center justify-center text-white px-6"
      style={{ backgroundImage: "url('https://images.unsplash.com/photo-1526374965328-7f61d4dc18c5?auto=format&fit=crop&w=1600&q=80')" }}>
      
      {/* Intro Section */}
      <motion.div
        initial={{ opacity: 0, y: -50 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 1 }}
        className="text-center mb-10"
      >
        <h1 className="text-5xl font-bold drop-shadow-lg">Hi, I'm Noor 👋</h1>
        <p className="text-lg mt-4 max-w-2xl mx-auto drop-shadow-md">
          Passionate about Data Engineering, Cloud Technologies & DevOps. I love building scalable systems and solving real-world problems.
        </p>
      </motion.div>

      {/* Tech Stack Section */}
      <motion.div
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ duration: 1.2, delay: 0.5 }}
        className="grid grid-cols-2 md:grid-cols-4 gap-6 mb-12"
      >
        {techStacks.map((stack, index) => (
          <Card key={index} className="bg-white/10 backdrop-blur-lg border border-white/20 shadow-lg text-center rounded-2xl p-6">
            <CardContent className="flex flex-col items-center">
              <stack.icon className="w-10 h-10 mb-3 text-white" />
              <p className="text-lg font-semibold">{stack.name}</p>
            </CardContent>
          </Card>
        ))}
      </motion.div>

      {/* Contact Section */}
      <motion.div
        initial={{ opacity: 0, y: 50 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 1.3, delay: 0.8 }}
        className="flex gap-6"
      >
        <Button variant="outline" className="bg-white/20 hover:bg-white/30 border-white/30 text-white">
          <Github className="w-5 h-5 mr-2" /> GitHub
        </Button>
        <Button variant="outline" className="bg-white/20 hover:bg-white/30 border-white/30 text-white">
          <Linkedin className="w-5 h-5 mr-2" /> LinkedIn
        </Button>
        <Button variant="outline" className="bg-white/20 hover:bg-white/30 border-white/30 text-white">
          <Mail className="w-5 h-5 mr-2" /> Contact
        </Button>
      </motion.div>
    </div>
  );
}
