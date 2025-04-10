import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { useState } from "react";

export default function Dashboard() {
  const [loggedIn, setLoggedIn] = useState(false);

  const handleLogin = (e) => {
    e.preventDefault();
    setLoggedIn(true);
  };

  if (!loggedIn) {
    return (
      <div className="min-h-screen flex items-center justify-center bg-gray-100">
        <Card className="w-full max-w-sm p-4">
          <CardContent>
            <h2 className="text-xl font-bold mb-4">School Admin Login</h2>
            <form onSubmit={handleLogin} className="space-y-4">
              <Input type="text" placeholder="Username" required />
              <Input type="password" placeholder="Password" required />
              <Button type="submit" className="w-full">Login</Button>
            </form>
          </CardContent>
        </Card>
      </div>
    );
  }

  return (
    <div className="min-h-screen bg-gray-50 p-4">
      <h1 className="text-2xl font-bold mb-6">Welcome to the School Dashboard</h1>
      <div className="grid grid-cols-2 md:grid-cols-3 gap-4">
        <Card>
          <CardContent>
            <h2 className="font-semibold">Learners</h2>
            <p>Manage student details, registration, and classes.</p>
          </CardContent>
        </Card>
        <Card>
          <CardContent>
            <h2 className="font-semibold">Exams & Reports</h2>
            <p>Enter marks, generate termly reports.</p>
          </CardContent>
        </Card>
        <Card>
          <CardContent>
            <h2 className="font-semibold">SMS Alerts</h2>
            <p>Send exam results, reminders, and updates.</p>
          </CardContent>
        </Card>
        <Card>
          <CardContent>
            <h2 className="font-semibold">Finance</h2>
            <p>Track fees, balances, and generate receipts.</p>
          </CardContent>
        </Card>
        <Card>
          <CardContent>
            <h2 className="font-semibold">Teachers</h2>
            <p>Assign subjects, manage performance records.</p>
          </CardContent>
        </Card>
        <Card>
          <CardContent>
            <h2 className="font-semibold">Parents</h2>
            <p>Enable parent access to academic progress and messages.</p>
          </CardContent>
        </Card>
      </div>
    </div>
  );
}



