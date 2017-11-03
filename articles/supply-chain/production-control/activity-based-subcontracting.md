---
title: "Podwykonawstwo działań"
description: "W tym temacie opisano szczegółowo, jak używać działań podwykonawczych w przepływie produkcji dla produkcji oszczędnej."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 000bfcf5c3daea75fc257374dd471c62e94fbc16
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="activity-based-subcontracting"></a>Podwykonawstwo działań

[!include[banner](../includes/banner.md)]


W tym temacie opisano szczegółowo, jak używać działań podwykonawczych w przepływie produkcji dla produkcji oszczędnej.

W programie Microsoft Dynamics 365 for Finance and Operations istnieją dwa podejścia do podwykonawstwa: zlecenia produkcyjne i produkcja oszczędna (lean manufacturing). W ujęciu z perspektywy produkcji oszczędnej praca podwykonawcza jest modelowana jako usługa powiązana z działaniem w przepływie produkcji. Wprowadzono specjalny typ grupy kosztów o nazwie **Outsourcing bezpośredni**, a usługi podwykonawcze nie są już częścią listy składowej (BOM). Rachunek kosztów pracy podwykonawczej jest w pełni zintegrowany z rozwiązaniem wyceny dla produkcji oszczędnej.

## <a name="production-flows-that-involve-subcontractors"></a>Przepływy produkcji z udziałem podwykonawców
Podstawowa zasada przepływu produkcji nie zmienia się w przypadku wykonywania działań przez podwykonawców. Materiał nadal przepływa między lokalizacjami, działania procesu przekształcają materiał na produkty, a działania przeniesienia przemieszczają materiał lub produkty z jednej lokalizacji do drugiej. Lokalizacje i komórki robocze można modelować jako zarządzane przez dostawcę, przypisując konto dostawcy do magazynu lub do zasobu w grupie zasobów.  

Dzięki tym możliwościom produkcja oszczędna nie wymaga żadnych szczególnych funkcji do obsługi przepływu materiałów i produktów. Wszystkie możliwe scenariusze z dostawcami jako dostarczycielami usług produkcji lub transportu mogą być modelowane w oparciu o architekturę przepływu produkcji i działań.  

Na przykład podwykonawca działa z supermarketu umieszczonego u podwykonawcy. Gdy jednostki załadunkowe są opróżniane w podwykonawcy, karty Kanban są zwracane do komórki montażowej wraz z następną wysyłką. Następnie supermarket u podwykonawcy jest uzupełniany. Przeniesienia do i od podwykonawcy mogą być modelowane jako jawne działania przeniesienia umożliwiające proces pobrania i wysyłki. Jeśli jawna rejestracja nie jest wymagana do obsługi fizycznego transportu, działania przeniesienia można pominąć.  

Można wykorzystywać podwykonawcę do równoważenia obciążenia łącznych zdolności produkcyjnych w przepływie produkcji. Na przykład przepływ produkcji jest modelowana przy użyciu reguł zaplanowanych kart Kanban. Planista używa tablicy planowania Kanban, aby zaplanować i zrównoważyć obciążenie obu komórek roboczych na żądanie. Planista również monitoruje skonsolidowany harmonogram dostaw dla supermarketu na stronie **Harmonogram dostaw**. Można modelować wielu podwykonawców w jednym lub wielu przepływach produkcji oraz może istnieć wiele reguł Kanban używanych w celu dostarczania tego samego produktu do tej samej lokalizacji poprzez różne działania. Planista można przekonwertować karty Kanban na alternatywną regułę Kanban, tak aby zadanie w systemie Kanban, które zostało pierwotnie utworzone dla wewnętrznej produkcji, zaplanować dla innego procesu. W rzeczywistości podwykonawczy charakter komórki roboczej nie ma wpływu na przepływ produkcji. Ta sama zasada pracy obowiązuje dla dwóch równoległych wewnętrznych komórek roboczych i dla dwóch komórek podwykonawstwa.   

Jak każde inne działanie w przepływie produkcji, działania podwykonawcze mogą zużywać oraz dostarczać materiały i produkty należące do zapasów, nienależące do zapasów (praca w toku \[PWT\]) i półprodukty. We wszystkich przypadkach procesy planowania i wykonywania działań podwykonawczych są takie same. Ponadto w tych procesach przetwarzanie odbywa się tak samo, jak w procesach pracy wewnętrznej.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Proces zakupu działań (usług) podwykonawczych
Proces zakupu działań podwykonawczych opiera się na fizycznym przepływie materiałów, który jest rejestrowany przez postęp zadania w systemie Kanban, na przykład operacje rozpoczęcia i zakończenia. Przepływ finansowy, na przykład koszty prac podwykonawczych, jest dodatkowym przepływem naśladującym przepływ fizyczny. W tym samym czasie proces zakupu jest niezależnym procesem, który pozwala na ręczne dopasowywanie dokumentów zakupu na każdym kroku. Oto przebieg procesu zakupu działań podwykonawczych:

1.  Tworzenie umowy zakupu. Umowa zakupu jest tworzona dla usługi i łączona z działaniem w przepływie produkcji.
2.  Umożliwia tworzenie zamówienia zakupu. Dla usługi można utworzyć zamówienie zakupu zwolnienia w oparciu o zaplanowane zadania w systemie Kanban. Zadania dla tej samej usługi mogą być grupowane do wierszy zamówienia zakupu według dnia, tygodnia lub miesiąca. Wiersze zamówienia zakupu mogą być tworzone w dowolnym momencie po utworzeniu zadań Kanban. Wiersze zamówienia zakupu mogą być tworzone nawet po fakcie. Tę opcję zaznacza się zazwyczaj, jeżeli podwykonawca dostarcza usługi bez dodatkowego powiadomienia, tylko w oparciu o otrzymywane karty Kanban. W takim przypadku można zminimalizować odchylenia między zamówieniem zakupu a fakturą.
3.  Generowanie kart Kanban, materiału i listy pobrania do wysyłania podwykonawcy w celu przygotowania do przetwarzania. W oparciu o szczegółowo wymodelowany przepływ produkcji następuje przygotowanie tablicy Kanban do działań procesu przy użyciu listy pobrania i funkcji przygotowania. Alternatywnie dla zadań przeniesienia przygotowanie odbywa się na tablicy Kanban przy użyciu listy pobrania i operacji rozpoczęcia lub zakończenia. W przypadku materiału należącego do zapasów oba procesy mogą być obsługiwane przez proces pobrania i wysyłki w systemie WMS. Na żądanie można utworzyć list przewozowy.
4.  Generowanie jednostek załadunkowych Kanban i kart Kanban. Po zakończeniu przetwarzania karty są zwracane od podwykonawcy. Zwykle karty zawierają dokument dostawy, która określa wysłany fizyczny materiał. Odwołanie do świadczonych usług nie jest wymagane. Przybycie materiału lub produktu do klienta jest rejestrowane na tablicy Kanban, w zależności od kart Kanban. (Zależnie od wymodelowanych działań jest używana tablica Kanban dla działań procesu lub tablica Kanban dla zadań przeniesienia).
5.  Tworzenie podsumowania przyjęcia. Podsumowanie przyjęcia może zastąpić dokument dostawy na otrzymane usługi. Podsumowania przyjęć mogą być generowane w oparciu o ukończone zadania Kanban dla działania podwykonawczego w wybranym okresie. Dla każdego przyjęcia z zadania są tworzone podsumowania dla odnośnego wiersza zamówienia zakupu. Podsumowanie przyjęcia może być drukowane i wysyłane podwykonawcy jako potwierdzenie przyjęcia.
6.  Generowanie faktury.

Proces kończy się z chwilą zafakturowania podwykonawcy za okres. Uzgadnianie faktury jest wykonywane względem utworzonych podsumowań przyjęć. Ponieważ podsumowania przyjęć reprezentują dokładne fizyczne przyjęcie materiału, uzgadnianie trzyelementowe jest uproszczone.

## <a name="configuring-activities-for-subcontracting"></a>Konfigurowanie działań podwykonawczych
W sekcjach poniżej opisano, jak skonfigurować działania podwykonawcze.

### <a name="subcontracted-services"></a>Usługi podwykonawcze

Element płatności używany w podwykonawstwie działań musi być produktem o następujących właściwościach:

-   **Typ produktu:** Usługa
-   **Grupa modeli magazynu:** Niemagazynowe

Ten wymóg wymusza użycie modelu zapasów FIFO (pierwszy na wejściu, pierwszy na wyjściu). **Uwaga:** W celu obliczania kosztów produktów musi być zdefiniowany standardowy koszt usługi. Wymagana jest umowa zakupu z dostawcą. W przeciwnym razie usługa nie może być wykorzystywana w podwykonawstwie działań.

### <a name="subcontracted-process-activities"></a>Działania procesu podwykonawczego

Aby skonfigurować działanie procesu jako działanie podwykonawcze, wykonaj następujące kroki.

1.  Konfigurowanie podwykonawczej komórki roboczej. Aby skonfigurować komórkę roboczą jako podwykonawczą, należy utworzyć zasób o typie **Dostawca** i skojarzyć go z komórką roboczą (grupą zasobów). Do komórki roboczej należy przypisać kategorię kosztu czasu wykonywania o typie grupy kosztów **Outsourcing bezpośredni**. Kategorie kosztów dla konfiguracji i ilości nie są wymagane.
2.  Po utworzeniu działania procesu i powiązaniu go z podwykonawczą komórką roboczą należy skonfigurować usługę dla działania, zanim będzie można aktywować wersję przepływu produkcji. Ten krok wykonuje się na stronie **Szczegóły** **dotyczące działania**. Dla działań skojarzonych z podwykonawczą komórką roboczą jest wyświetlana skrócona karta **Warunki usługi**. Na tej skróconej karcie dodaj domyślną usługę obowiązującą dla wszystkich pozycji wyjściowych. Jeśli określone pozycje wyjściowe wymagają innych usług lub innych parametrów obliczania usług (na przykład innego wskaźnika usługi), można dodać inne usługi do działania.

## <a name="subcontracted-transfer-activities"></a>Działania przeniesienia podwykonawczego
Działanie przeniesienia jest konfigurowane jako działanie podwykonawcze w zależności od ustawienia **Transportowane przez** w opcjach działania przeniesienia. Dostępne są następujące opcje:

-   **Spedytor** — działanie jest podwykonawcze, jeśli przeniesienie z magazynu jest zarządzane przez dostawcę (zgodnie z definicją we właściwości magazynu). Wszystkie wybrane umowy zakupu usług muszą mieć ten sam identyfikator dostawcy jako magazyn.
-   **Adresat** — działanie jest podwykonawcze, jeśli przeniesienie do magazynu jest zarządzane przez dostawcę (zgodnie z definicją we właściwości magazynu). Wszystkie wybrane umowy zakupu usług muszą mieć ten sam identyfikator dostawcy jako magazyn.
-   **Przewoźnik** — działanie jest podzlecane dowolnemu dostawcy świadczącemu usługę. Aby działanie było prawidłowe, przewoźnik musi zostać utworzony dla modułu zarządzania magazynem i musi mieć przypisane konto dostawcy.

Jeśli chodzi o działania procesu, należy skonfigurować domyślną usługę dla podwykonawczych działań przeniesienia na skróconej karcie **Warunki usługi** na stronie **Szczegóły** **dotyczące działania**.

## <a name="service-quantity-calculation"></a>Obliczanie ilości usługi
Cały proces zakupu opiera się na odwołaniu do pozycji w usłudze. To odwołanie do pozycji jest mierzone w jednostce miary usługi. Usługi są zwykle mierzone za pomocą liczby usług (jednostek) lub czasu. Aby obliczyć liczbę usług (w oparciu o zarejestrowane ukończenie zadań w systemie Kanban), można użyć następujących metod:

-   **Obliczenie oparte na liczbie zadań** — jedno zadanie Kanban jest równe *n* jednostkom usługi, bez względu na dostarczoną ilość produktu. W produkcji oszczędnej jedno zadanie odpowiada jednej jednostce załadunkowej. Ta metoda obliczania stosuje się do wszystkich usług mających stałą ceny za jednostkę załadunkową. Dlatego ta metoda zazwyczaj stosuje się do działań przeniesienia. Jednakże można ją także stosować do działań procesów, w których są przetwarzane całe jednostki załadunkowe.
-   **Obliczenie oparte na ilości produktu** — ilość usługi jest względna wobec zaplanowanej/dostarczonej ilości produktu. Podczas obliczania dostarczonej ilości produktu ilości błędne można uwzględniać lub wykluczać. Ta metoda obliczania stosuje się do wszystkich przypadków, gdzie uzgodniono cenę usługi na jednostkę przetworzonego produktu.
-   **Obliczenie oparte na czasie działania** — teoretyczne czasy działań są obliczane na podstawie czasów przetwarzania w działaniu, łącznej przetworzonej ilości i wskaźnika produktywności przetworzonego produktu. Ta metoda obliczania stosuje się do usług, które są opłacane godzinowo i mają różne czasy dla każdego przetwarzanego produktu.

## <a name="cost-accounting-of-subcontracted-services"></a>Rachunek kosztów usług podwykonawczych
Podczas księgowaniu podsumowania przyjęcia lub dokumentu dostawy od dostawcy z zamówienia zakupu utworzonego dla przepływu produkcji (innymi słowy z zamówienia zakupu wygenerowanego na podstawie zadań w systemie Kanban dla działań podwykonawczych) wartość przyjęcia jest rozliczana na kontach PWT przepływu produkcji. Odchylenia faktur księguje się również na kontach przepływu produkcji. Wprowadzono funkcjonalność kategorii kosztu dla prac podwykonawczych. Ta kategoria kosztu umożliwia przejrzyste śledzenie wartości prac podwykonawczych, które są przydzielone do PWT i zużywane w ciągu okresu.  

Wycena wsteczna produkcji oszczędnej na koniec okresu wyceny powoduje obliczanie rzeczywistego odchylenia wytwarzanych produktów od przepływu produkcji w okresie wyceny.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Modelowanie przeniesień jako działań podwykonawczych
Ludzie często uważają transport za nieproduktywny i sądzą, że nie dodaje wartości. Jednakże porównując koszty podwykonawstwa z kosztami produkcji wewnętrznej, trzeba uwzględniać koszty dodatkowych działań transportowych. Przepływ produkcji, który obejmuje wiele lokalizacji i wymaga usług transportowych, powinien modelować koszt transportu jako składnik kosztu dostarczenia produktów do odbiorcy. 

Podwykonawstwo działań w produkcji oszczędnej pozwala zintegrować przewoźników i dostawców usług transportowych, którzy przemieszczają materiały i produkty między lokalizacjami przepływu produkcji. Modelując działanie przeniesienia, można przypisać przewoźnika lub dostawcę. Działania/zadanie przeniesienia opiera się na usłudze i umowie sprzedaży. Można tworzyć zamówienia zakupu i podsumowania przyjęć na podstawie faktycznych zadań przeniesienia. Ta funkcjonalność jest taka sama, jak funkcjonalność działań procesu podwykonawczego.  

W związku z tym program Finance and Operations obsługuje teraz obliczanie BOM, które obejmuje usługi transportowe, tworzenie powiązanych zamówień zakupu, zintegrowaną rejestrację przyjęć oraz integrację kosztów usług transportowych w wycenie przepływu produkcji.




