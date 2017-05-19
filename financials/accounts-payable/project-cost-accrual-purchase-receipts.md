---
title: "Naliczanie kosztów projektu w przyjęciach zakupów"
description: "W tym temacie opisano, jak koszty projektu naliczone z przyjęć zakupów można śledzić w programie Microsoft Dynamics 365 for Operations."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 9caa1f7818e21ae448effc6169e1fe02c8edf510
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="project-cost-accrual-on-purchase-receipts"></a>Naliczanie kosztów projektu w przyjęciach zakupów

[!include[banner](../includes/banner.md)]


W tym temacie opisano, jak koszty projektu naliczone z przyjęć zakupów można śledzić w programie Microsoft Dynamics 365 for Operations. 

Faktury za projekt często przychodzą później niż są dostarczane towary i usługi, co może mieć znaczący wpływ na kluczowe wskaźniki wydajności (KPI) projektu. Ważna jest możliwość śledzenia tych transakcji w sprawozdaniach finansowych i raportach z projektu.

Ilustruje to przykładowy scenariusz opisany poniżej. 

Firma Contoso Consulting rozpoczęła nowy projekt wdrożenia chmury. Utworzono zamówienie zakupu na zakup komputera do projektu. Komputer będzie kosztować 1500 USD, a usługi instalacyjne dodatkowe 150 USD. Dostawca dostarczył i zainstalował komputer, ale faktura jeszcze nie dotarła do Contoso Consulting. Kierownik projektu chciałby widzieć naliczenie kosztów projektu w kwocie 1650 USD, zanim faktura zostanie dostarczona. Ponadto koszt powinien znaleźć odzwierciedlenie w sprawozdaniu finansowym firmy na koniec miesiąca. 

Dla celów sprawozdawczości naliczony koszt musi być zarejestrowany na poziomach finansowym i projektu. W programie Dynamics 365 for Operations finansową aktualizację przyjęcia produktu można śledzić w kategoriach towaru i zaopatrzenia. 

W przypadku towarów na stronie **Parametry modułu rozrachunków z dostawcami** zaznacz opcję **Księguj przyjęcia produktów w księdze**.
[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png) 

Dla kategorii zaopatrzenia na stronie **Reguła kategorii** zaznacz zasady **Zakupy**, a następnie dla każdej kategorii zaopatrzenia zaznacz opcję **Naliczanie wydatku na zakup w momencie przyjęcia**.
[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png) 

Konta **Koszty zakupu niezafakturowane** i **Naliczenie zakupu** w oknie **Ustawienia księgowania** będą używane podczas księgowana załączników związanych z przyjęciem produktu.
[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png) 

W tym samym scenariuszu zobaczmy, jak księgowanie przyjęcia produktu wpłynie na księgę główną i informacji o projekcie. 

**Krok 1:** Utwórz i potwierdź nowe zamówienie zakupu dla projektu, aby zarejestrować zakup komputera za 1500 USD i usług instalacyjnych za 150 USD.
[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png) 

Po potwierdzeniu zamówienia zakupu zostaną dla projektu utworzone transakcje na ustalony koszt. 
[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png) 

> [!NOTE]
> Transakcje na ustalony koszt będą miały w polu **Źródło transakcji** ustawioną wartość **Zamówienie zakupu**. Utworzenie i potwierdzenie zamówienia zakupu nie tworzy transakcji dla projektu. 

**Krok 2:** Towary i usługi zostają dostarczone i następuje zarejestrowanie przyjęcia produktu. 

Zaksięgowanie przyjęcia produktu spowoduje wygenerowanie załącznika i jego zaksięgowanie w księdze. Załącznik zostanie zapisany po stronie debetowej na koncie niezafakturowanych kosztów zakupu, a po stronie uznaniowej na koncie naliczeń zakupu. 
[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)

> [!NOTE]
> W celu zaksięgowania przyjęcia produktu będzie używana konfiguracja księgowania kategorii zaopatrzenia i produktów, a nie konfiguracja księgowania kategorii projektu. W celu właściwego wykazania finansowego wpływu naliczeń zakupu należy odpowiednio dopasować tę konfigurację. 

Na stronie **Kategoria zaopatrzenia** można zamapować kategorie zaopatrzenia na kategorie projektu.
[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)

**Krok 3:** Utwórz wersję roboczą faktury od dostawcy. 

W programie Dynamics 365 for Operations zaksięgowanie przyjęcia produktu nie wpływa na informacje o projekcie. Aby obejść to zachowanie, można wygenerować wersję roboczą faktury od dostawcy natychmiast po zaksięgowaniu przyjęcia zakupu. Przejdź do strony **Zamówienie zakupu** &gt; karta **Faktura** &gt; **Generuj** &gt; **fakturę**. Zostanie utworzony dokument oczekującej faktury, który aktualizuje dane projektu. 

Utworzenie wersji roboczej faktury od dostawcy spowoduje generowanie oczekujących transakcji projektu. 
[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png) 

Na stronie **Ustalony koszt** rekordy utworzone w kroku 1 zostaną zamknięte, a program utworzy nowe rekordy odzwierciedlające potwierdzenie kosztów pochodzące z oczekującej faktury od dostawcy. Pole **Źródło transakcji** dotyczące ustalonego kosztu zostanie ustawione na wartość **Faktura od dostawcy**.
[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)

Faktura od dostawcy pozostanie w stanie oczekiwania do momentu nadejścia rzeczywistej faktury od dostawcy.




