# creative-launch
import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Textarea } from "@/components/ui/textarea";

function LandingPage({ onStart }: { onStart: () => void }) {
  return (
    <div className="min-h-screen flex flex-col items-center justify-center p-8 bg-gradient-to-br from-blue-100 to-purple-200">
      <h1 className="text-4xl md:text-5xl font-bold mb-4 text-center">Welcome to CreativeLaunch</h1>
      <p className="text-lg md:text-xl text-center max-w-xl mb-6">
        Empowering creatives through digital tools, mentorship, and collaboration.
      </p>
      <Button className="text-lg px-6 py-3" onClick={onStart}>
        Get Started
      </Button>
    </div>
  );
}

function Dashboard() {
  return (
    <div className="grid grid-cols-1 md:grid-cols-2 gap-6 p-6">
      <Card className="rounded-2xl shadow-md">
        <CardContent className="space-y-4">
          <h2 className="text-xl font-bold">Create Your Profile</h2>
          <Input placeholder="Name" />
          <Input placeholder="Creative Field (e.g., Music, Design)" />
          <Textarea placeholder="Bio and Portfolio Summary" />
          <Button>Create Profile</Button>
        </CardContent>
      </Card>

      <Card className="rounded-2xl shadow-md">
        <CardContent className="space-y-4">
          <h2 className="text-xl font-bold">Mentorship & Workshops</h2>
          <p>Join sessions, find a mentor, or become one!</p>
          <Button>Browse Workshops</Button>
          <Button variant="outline">Apply as Mentor</Button>
        </CardContent>
      </Card>

      <Card className="rounded-2xl shadow-md">
        <CardContent className="space-y-4">
          <h2 className="text-xl font-bold">Discover Tools</h2>
          <p>Explore essential gear and apps for your work.</p>
          <Button>Explore Tools</Button>
        </CardContent>
      </Card>

      <Card className="rounded-2xl shadow-md">
        <CardContent className="space-y-4">
          <h2 className="text-xl font-bold">Collaborate & Network</h2>
          <p>Find and connect with other creatives.</p>
          <Button>Find Creatives</Button>
        </CardContent>
      </Card>

      <Card className="rounded-2xl shadow-md">
        <CardContent className="space-y-4">
          <h2 className="text-xl font-bold">Launch Campaign</h2>
          <Input placeholder="Campaign Title" />
          <Textarea placeholder="Describe your campaign..." />
          <Button>Start Campaign</Button>
        </CardContent>
      </Card>

      <Card className="rounded-2xl shadow-md">
        <CardContent className="space-y-4">
          <h2 className="text-xl font-bold">Promote Yourself</h2>
          <p>Run social media ads or promote organically.</p>
          <Button>Launch Ad</Button>
        </CardContent>
      </Card>
    </div>
  );
}

export default function CreativeLaunchApp() {
  const [started, setStarted] = React.useState(false);

  return started ? <Dashboard /> : <LandingPage onStart={() => setStarted(true)} />;
}
