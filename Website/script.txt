document.addEventListener("DOMContentLoaded", () => {
  // Footer year
  const yearEl = document.getElementById("year");
  if (yearEl) yearEl.textContent = new Date().getFullYear();

  // Accordion behaviour (only one FAQ open at a time)
  const faqs = Array.from(document.querySelectorAll("details.faq"));
  faqs.forEach((d) => {
    d.addEventListener("toggle", () => {
      if (!d.open) return;
      faqs.forEach((other) => {
        if (other !== d) other.open = false;
      });
    });
  });

  // Social placeholders
  document.querySelectorAll(".social-btn").forEach((btn) => {
    btn.addEventListener("click", () => {
      alert("Add your social media links here (Facebook / Instagram / X).");
    });
  });
});
