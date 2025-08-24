# ollama-code
v1
CodePreview
import React, { useState } from 'react';
import { Button } from "/components/ui/button"
import { Card, CardContent, CardDescription, CardFooter, CardHeader, CardTitle } from "/components/ui/card"
import { Shield, Users, Clock, Star, Play, Check } from "lucide-react"

export default function SaaSLandingPage() {
  const [activePlan, setActivePlan] = useState('pro');

  const features = [
    {
      icon: <Shield className="h-8 w-8 text-blue-500" />,
      title: "Enterprise Security",
      description: "Bank-level encryption and compliance to keep your data safe."
    },
    {
      icon: <Users className="h-8 w-8 text-blue-500" />,
      title: "Team Collaboration",
      description: "Work seamlessly with your team in real-time from anywhere."
    },
    {
      icon: <Clock className="h-8 w-8 text-blue-500" />,
      title: "24/7 Support",
      description: "Our experts are always available to help you succeed."
    },
    {
      icon: <Star className="h-8 w-8 text-blue-500" />,
      title: "Premium Quality",
      description: "Industry-leading tools designed for maximum performance."
    }
  ];

  const testimonials = [
    {
      quote: "This platform transformed our workflow. We've seen a 40% increase in productivity since implementation.",
      author: "Sarah Johnson",
      role: "CTO, TechCorp",
      avatar: "SJ"
    },
    {
      quote: "The best investment we've made. Customer support is exceptional and the features are constantly improving.",
      author: "Michael Chen",
      role: "Product Manager, InnovateX",
      avatar: "MC"
    },
    {
      quote: "Implementation was seamless and the ROI was immediate. Highly recommended for growing businesses.",
      author: "Emma Rodriguez",
      role: "Founder, StartUpScale",
      avatar: "ER"
    }
  ];

  const pricingPlans = [
    {
      name: "Starter",
      price: "$29",
      period: "per month",
      description: "Perfect for small teams getting started",
      features: [
        "Up to 5 users",
        "Basic analytics",
        "Email support",
        "1GB storage"
      ],
      cta: "Get Started",
      popular: false
    },
    {
      name: "Professional",
      price: "$79",
      period: "per month",
      description: "For growing businesses",
      features: [
        "Up to 20 users",
        "Advanced analytics",
        "Priority support",
        "10GB storage",
        "API access"
      ],
      cta: "Try Free for 14 Days",
      popular: true
    },
    {
      name: "Enterprise",
      price: "Custom",
      period: "",
      description: "For large organizations",
      features: [
        "Unlimited users",
        "Custom analytics",
        "24/7 dedicated support",
        "Unlimited storage",
        "Custom integrations",
        "SLA guarantee"
      ],
      cta: "Contact Sales",
      popular: false
    }
  ];

  return (
    <div className="min-h-screen bg-white">
      {/* Hero Section */}
      <section className="w-full py-12 md:py-24 lg:py-32 xl:py-48 bg-gradient-to-r from-blue-50 to-indigo-50">
        <div className="container px-4 md:px-6">
          <div className="flex flex-col items-center space-y-4 text-center">
            <div className="space-y-2">
              <h1 className="text-3xl font-bold tracking-tighter sm:text-4xl md:text-5xl lg:text-6xl/none">
                Transform Your Business with Our Platform
              </h1>
              <p className="mx-auto max-w-[700px] text-gray-500 md:text-xl dark:text-gray-400">
                All-in-one solution to streamline operations, boost productivity, and drive growth for modern businesses.
              </p>
            </div>
            <div className="space-x-4">
              <Button size="lg" className="bg-blue-600 hover:bg-blue-700">
                Start Free Trial
              </Button>
              <Button variant="outline" size="lg">
                <Play className="mr-2 h-4 w-4" /> Watch Demo
              </Button>
            </div>
          </div>
        </div>
      </section>

      {/* Features Section */}
      <section className="w-full py-12 md:py-24 lg:py-32">
        <div className="container px-4 md:px-6">
          <div className="text-center mb-12">
            <h2 className="text-3xl font-bold tracking-tighter sm:text-5xl">
              Powerful Features
            </h2>
            <p className="mt-4 mx-auto max-w-[600px] text-gray-500 md:text-xl">
              Everything you need to grow your business efficiently
            </p>
          </div>
          <div className="grid gap-8 sm:grid-cols-2 lg:grid-cols-4">
            {features.map((feature, index) => (
              <Card key={index} className="border-0 shadow-none">
                <CardContent className="p-6 text-center">
                  <div className="flex justify-center mb-4">
                    {feature.icon}
                  </div>
                  <h3 className="text-xl font-bold mb-2">{feature.title}</h3>
                  <p className="text-gray-500">{feature.description}</p>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Testimonials Section */}
      <section className="w-full py-12 md:py-24 lg:py-32 bg-gray-50">
        <div className="container px-4 md:px-6">
          <div className="text-center mb-12">
            <h2 className="text-3xl font-bold tracking-tighter sm:text-5xl">
              Trusted by Industry Leaders
            </h2>
            <p className="mt-4 mx-auto max-w-[600px] text-gray-500 md:text-xl">
              Join thousands of satisfied customers transforming their businesses
            </p>
          </div>
          <div className="grid gap-8 sm:grid-cols-2 lg:grid-cols-3">
            {testimonials.map((testimonial, index) => (
              <Card key={index} className="border-0 shadow-lg">
                <CardContent className="p-6">
                  <div className="flex items-center mb-4">
                    <div className="flex">
                      {[...Array(5)].map((_, i) => (
                        <Star key={i} className="h-5 w-5 fill-yellow-400 text-yellow-400" />
                      ))}
                    </div>
                  </div>
                  <p className="text-gray-500 mb-6">"{testimonial.quote}"</p>
                  <div className="flex items-center">
                    <div className="bg-gray-200 border-2 border-dashed rounded-xl w-16 h-16 flex items-center justify-center mr-4">
                      <span className="text-lg font-bold">{testimonial.avatar}</span>
                    </div>
                    <div>
                      <p className="font-bold">{testimonial.author}</p>
                      <p className="text-gray-500">{testimonial.role}</p>
                    </div>
                  </div>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Pricing Section */}
      <section className="w-full py-12 md:py-24 lg:py-32">
        <div className="container px-4 md:px-6">
          <div className="text-center mb-12">
            <h2 className="text-3xl font-bold tracking-tighter sm:text-5xl">
              Simple, Transparent Pricing
            </h2>
            <p className="mt-4 mx-auto max-w-[600px] text-gray-500 md:text-xl">
              Choose the plan that works best for your team
            </p>
          </div>
          <div className="grid gap-8 sm:grid-cols-2 lg:grid-cols-3">
            {pricingPlans.map((plan, index) => (
              <Card 
                key={index} 
                className={`relative ${plan.popular ? 'border-2 border-blue-500 shadow-xl' : ''}`}
              >
                {plan.popular && (
                  <div className="absolute top-0 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-blue-500 text-white text-xs font-bold px-4 py-1 rounded-full">
                    MOST POPULAR
                  </div>
                )}
                <CardHeader>
                  <CardTitle className="text-2xl">{plan.name}</CardTitle>
                  <div className="mt-4">
                    <span className="text-4xl font-bold">{plan.price}</span>
                    {plan.period && <span className="text-gray-500"> {plan.period}</span>}
                  </div>
                  <CardDescription>{plan.description}</CardDescription>
                </CardHeader>
                <CardContent>
                  <ul className="space-y-2">
                    {plan.features.map((feature, featureIndex) => (
                      <li key={featureIndex} className="flex items-center">
                        <Check className="h-5 w-5 text-green-500 mr-2" />
                        <span>{feature}</span>
                      </li>
                    ))}
                  </ul>
                </CardContent>
                <CardFooter>
                  <Button 
                    className={`w-full ${plan.popular ? 'bg-blue-600 hover:bg-blue-700' : ''}`}
                    variant={plan.popular ? "default" : "outline"}
                  >
                    {plan.cta}
                  </Button>
                </CardFooter>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Final CTA Section */}
      <section className="w-full py-12 md:py-24 lg:py-32 bg-gradient-to-r from-blue-500 to-indigo-600">
        <div className="container px-4 md:px-6">
          <div className="flex flex-col items-center space-y-4 text-center">
            <div className="space-y-2">
              <h2 className="text-3xl font-bold tracking-tighter sm:text-4xl md:text-5xl text-white">
                Ready to Get Started?
              </h2>
              <p className="mx-auto max-w-[600px] text-blue-100 md:text-xl">
                Join thousands of satisfied customers transforming their businesses today.
              </p>
            </div>
            <div className="w-full max-w-sm space-y-2">
              <Button size="lg" className="w-full bg-white text-blue-600 hover:bg-gray-100">
                Start Your Free Trial
              </Button>
              <p className="text-xs text-blue-100">
                No credit card required. Cancel anytime.
              </p>
            </div>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="py-6 w-full shrink-0 border-t">
        <div className="container px-4 md:px-6 flex flex-col md:flex-row items-center justify-between">
          <p className="text-xs text-gray-500">© 2023 SaaS Platform. All rights reserved.</p>
          <nav className="flex gap-4 mt-4 md:mt-0">
            <a className="text-xs hover:underline underline-offset-4" href="#">
              Terms of Service
            </a>
            <a className="text-xs hover:underline underline-offset-4" href="#">
              Privacy
            </a>
            <a className="text-xs hover:underline underline-offset-4" href="#">
              Contact
            </a>
          </nav>
        </div>
      </footer>
    </div>
  );
