# appbundle
bundle
import { Toaster } from "@/components/ui/sonner";
import { TooltipProvider } from "@/components/ui/tooltip";
import NotFound from "@/pages/NotFound";
import { Route, Switch } from "wouter";
import ErrorBoundary from "./components/ErrorBoundary";
import { ThemeProvider } from "./contexts/ThemeContext";
import Home from "./pages/Home";
import PatientDashboard from "./pages/PatientDashboard";
import PatientRegister from "./pages/PatientRegister";
import Shop from "./pages/Shop";
import OrderHistory from "./pages/OrderHistory";
import AdminDashboard from "./pages/AdminDashboard";
import AdminPatients from "./pages/AdminPatients";
import AdminProducts from "./pages/AdminProducts";
import AdminSales from "./pages/AdminSales";
import AdminCaregivers from "./pages/AdminCaregivers";

function Router() {
  return (
    <Switch>
      <Route path={"/"} component={Home} />
      <Route path={"/patient"} component={PatientDashboard} />
      <Route path={"/patient/register"} component={PatientRegister} />
      <Route path={"/patient/shop"} component={Shop} />
      <Route path={"/patient/orders"} component={OrderHistory} />
      <Route path={"/admin"} component={AdminDashboard} />
      <Route path={"/admin/patients"} component={AdminPatients} />
      <Route path={"/admin/products"} component={AdminProducts} />
      <Route path={"/admin/sales"} component={AdminSales} />
      <Route path={"/admin/caregivers"} component={AdminCaregivers} />
      <Route path={"/404"} component={NotFound} />
      <Route component={NotFound} />
    </Switch>
  );
}

function App() {
  return (
    <ErrorBoundary>
      <ThemeProvider
        defaultTheme="light"
      >
        <TooltipProvider>
          <Toaster />
          <Router />
        </TooltipProvider>
      </ThemeProvider>
    </ErrorBoundary>
  );
}

export default App;
