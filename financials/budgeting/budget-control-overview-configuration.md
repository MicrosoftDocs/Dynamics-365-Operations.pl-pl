---
title: "Omówienie kontroli budżetu"
description: "W tym artykule wprowadza kontroli budżetu i podano informacje ułatwiające konfigurowanie kontroli budżetu w usłudze Microsoft Dynamics 365 dla operacji, tak, że można zarządzanie środkami finansowymi."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 60493
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 04e0c066511c1fedf33784944441326201fc2df8
ms.lasthandoff: 03/31/2017


---

# <a name="budget-control-overview"></a>Omówienie kontroli budżetu

W tym artykule wprowadza kontroli budżetu i podano informacje ułatwiające konfigurowanie kontroli budżetu w usłudze Microsoft Dynamics 365 dla operacji, tak, że można zarządzanie środkami finansowymi.

<a name="overview"></a>Przegląd
--------

Kontrola budżetu w usłudze Microsoft Dynamics 365 dla operacji obsługuje zarządzanie środkami finansowymi organizacji za pomocą planu kont, przepływy pracy, grup użytkowników, dokumentów źródłowych i arkuszy, można konfigurować obliczanie dostępnych funduszy, cykle budżetu i progi. Dzięki kontroli organizacja może planować, zmierzyć, zarządzać i prognozować swoje zasoby finansowe w całym roku obrachunkowym. 

Po zatwierdzeniu budżetów w usłudze Dynamics 365 dla operacji, plany budżetu można użyć do wygenerowania wpisów do rejestru budżetu do rejestrowania budżetu wydatków dla organizacji. Alternatywnie można utworzyć lub zaimportować wpisy do rejestru budżetu z programu innej firmy, zamiast korzystać z funkcji planowania budżetu. 

Wydatki mogą być rejestrowane przy użyciu kont głównych i wymiarów finansowych. Można skonfigurować kontrolę nad całością wydatków, aby spełniać wymogi i zasady obowiązujące w organizacji, poprzez grupowanie kombinacji wymiarów finansowych i kont głównych. 

Poniższy wykres przedstawia miejsce kontroli budżetu w etapach typowego cyklu budżetu.

[![BudgetingCycle](./media/budgetingcycle-300x198.png)](./media/budgetingcycle.png) 

Można skonfigurować kontrolę budżetu, zależnie od kilku czynników:

-   **Wymiary finansowe** — Które wymiary finansowe są potrzebne do raportowania budżetu i wartości rzeczywistych oraz które wymiary finansowe są niezbędne do kontroli budżetu? Czy istnieją określone kombinacje wymiarów lub konta główne wymagające szczególnej uwagi? Na przykład, czy trzeba śledzić budżet do wartości rzeczywistych przez program i Centrum kosztów? Czy wydatki na podróże wymagają szczególnej uwagi?
-   **Czas** — Jaki przedział czasu (okres obrachunkowy, okres obrachunkowy od początku roku itd.) będzie używany do obliczania dostępnych środków budżetowych?
-   **Dokumenty źródłowe** jakie muszą zostać ocenione dokumentów źródłowych do kontroli budżetu? Dokumenty powinny być oceniane na linii lub na dokumencie?
-   **Obliczanie dostępnych środków** — Czy przy obliczaniu dostępnych środków budżetowych mają zostać uwzględnione dokumenty takie jak zapotrzebowania na zakup (przyszłe zobowiązanie niewiążące) i zamówienia zakupu (przyszłe zobowiązania wiążące)? Czy w obliczaniu dostępnych środków mają być uwzględniane dokumenty będące wersjami roboczymi?
-   **Uprawnienia zastępowania** — Kto ma uprawnienie do przekroczenia dostępnego budżetu?

Kontrola budżetu jest w pełni zintegrowany z usługą Dynamics 365 dla operacji. Z tego względu można oceniać dostępny budżet zarówno dla zakupów planowanych, jak i rzeczywistych. Dostępne są zapytania dotyczące budżetu i raporty. Dzięki temu użytkownicy mogą dokonywać oceny budżetu w całym cyklu budżetu oraz wprowadzać niezbędne zmiany w formie korekt budżetu lub przeniesień. Menedżer budżetu może również w razie potrzeby wyeksportować budżet i wartości rzeczywiste do programu Microsoft Excel, aby lepiej analizować i prognozować.

## <a name="configuring-budget-control"></a>Konfigurowanie kontroli budżetu
### <a name="budget-cycle-time-span"></a>Okres cyklu budżetu

Po skonfigurowaniu podstawowego budżetowania można zdefiniować czas lub okresy początkowy i końcowy dla budżetowania i kontroli budżetu na stronie **Okres cyklu budżetu**. Cykle budżetu często odpowiadają kalendarzom obrachunkowym, ale mogą obejmować lata obrachunkowe.

Następne kroki w konfiguracji są wykonywane na różnych zakładkach na **konfiguracji kontroli budżetu** strony.

### <a name="define-parameters"></a>Definiuj parametry

Na podstawie wymiarów finansowych włączonych dla budżetu można do kontrolowania budżetu używać wszystkich lub części wymiarów finansowych. 

Ponadto można określić domyślny przedział czasu (na przykład **Rok obrachunkowy**, **Od początku roku obrachunkowego**, **Okres obrachunkowy** lub **Kwartalnie**), który będzie objęty kontrolą budżetu w odnośnym okresie cyklu budżetu. Można również określić domyślnego menedżera budżetu oraz próg, o którego osiągnięciu użytkownicy będą powiadamiani. Wartości w tych polach będą używane jako wartości domyślne w każdej nowej regule kontroli budżetu lub nowo tworzonej grupie budżetu. Wartości domyślne można jednak zmienić dla poszczególnych grup i reguł. 

Sposoby tworzenia i rejestrowania budżetu w rejestrze budżetu pomagają określić okres wybierany podczas obliczania dostępnych środków budżetowych. Jeśli roczna kwota dla kombinacji wartości wymiarów jest obliczona i używana, lepszym rozwiązaniem może być podejście roku obrachunkowego lub okresu od początku roku obrachunkowego. Jednak jeśli organizacja, która tworzy budżety według okresu obrachunkowego lub alokuje do okresów obrachunkowych, chce mieć bardziej szczegółową kontrolę, warto rozważyć okresy roku obrachunkowego lub od początku roku obrachunkowego. 

Ponadto rolę przy definiowaniu konfiguracji odgrywa kultura organizacji w zakresie, w jakim odnosi się do budżetowania i kontroli budżetowej.

### <a name="over-budget-permissions"></a>Uprawnienia ponadbudżetowe

Następnie na karcie **Uprawnienia ponadbudżetowe** można określić grupy użytkowników. Można również określić, czy użytkownicy, którzy są członkami grupy, mają możliwość przekraczania budżetu. Można uniemożliwić użytkownikom przekraczanie budżetu ponad próg budżetu, który został ustawiony na stronie **Parametry budżetu**, lub zablokować przekraczanie budżetu o jakąkolwiek kwotę, bez względu na próg. Zależnie od sposobu, w jaki organizacja aktywnie zarządza swoimi wydatkami, te uprawnienia ułatwiają zarządzanie zasobami finansowymi. 

### <a name="budget-funds-available"></a>Dostępne środki budżetowe

Następnie na karcie **Dostępne środki budżetowe** można zdefiniować formułę, która będzie służyła do obliczania dostępnych środków budżetowych. Zależnie od tego, na ile konserwatywnie organizacja zarządza swoimi zasobami finansowymi albo jakie istnieją przepisy lub wymagania branży, w obliczeniach mogą być uwzględniane wersje robocze i niezaksięgowane dokumenty. 

> [!NOTE] 
> Jeśli obliczenie jest modyfikowany podczas cyklu budżetu, zmiany nie mają wpływu na wszelkich dokumentów, które wcześniej przeszły sprawdzania kontroli budżetu i zaksięgowanych lub zakończone.

### <a name="documents-and-journals"></a>Dokumenty i arkusze

Następnie na karcie **Dokumenty i arkusze** można wybrać, które dokumenty źródłowe i arkusze będą podlegać kontroli budżetu, i określić, czy kontrola nastąpi na poziomie wprowadzania wierszy czy całego dokumentu. 

Należy dopasować dokumenty źródłowe wybrane za pomocą pól wyboru dla sald uwzględnionych na potrzeby obliczania dostępnych środków budżetowych. Na przykład, jeśli wybrano opcję **rezerwy w budżecie dla przyszłych zobowiązań wiążących**, należy zaznaczyć opcję **zamówienia zakupu**. Podczas kontroli budżetu dla kwot i kont w wierszu zakupu, kategoria kontroli budżetu przypisana do rezerwacji ma wartość **przyszłe zobowiązanie wiążące**. Podczas kontroli budżetu dla kwot i kont w zapotrzebowaniu na zakup kategoria kontroli budżetu przypisana do rezerwacji ma wartość **Przyszłe zobowiązanie niewiążące**. 

Jeśli pozycje **Rezerwy w budżecie dla przyszłych zobowiązań wiążących** i/lub **Rezerwy w budżecie na przyszłe zobowiązania niewiążące** są uwzględniane w obliczaniu dostępnych środków budżetowych i muszą zostać uwzględnione za pośrednictwem księgowań w księdze głównej, należy włączyć ewidencję przyszłych zobowiązań kontraktowych na stronie **Parametry księgi głównej**.  

### <a name="assign-budget-models"></a>Przypisz modele budżetu

Następnie na karcie **Przypisz modele budżetu** można przypisać modele budżetu do okresów cykli budżetu, które mają być uwzględniane w kontroli budżetu.

### <a name="define-budget-control-rules"></a>Definiowanie reguł kontroli budżetu

Następnie na karcie **Definiowanie reguł kontroli budżetu** należy utworzyć konkretne reguły na podstawie wymiarów finansowych włączonych do kontroli budżetu. Na przykład aby skoncentrować się na wydatku lub zakresie wydatków działu, można za pomocą ustawień na tej karcie zdefiniować i obliczyć te wydatki. Dla każdej reguły kontroli budżetu można zdefiniować różne progi. 

> [!Important]
> Kontrola budżetu zostaną włączone dla dowolnego konta głównego z **zysków i strat**, **wydatków**, **przychody, bilansu, zobowiązań, kapitału własnego** lub **aktywów** typu. Jeśli ta karta zawiera regułę z pustymi kryteriami, kontrola budżetu zostanie włączona dla **wszystkich** kombinacje wymiarów finansowych, które zawierają konta główne o tych typach. Dlatego należy się upewnić, że tworzone reguły kontroli budżetu określają tylko zakresy kombinacji wymiarów finansowych, w których ważne jest włączenie kontroli budżetu.  

### <a name="select-main-accounts"></a>Wybór konta głównego

Jeśli na stronie **Definiuj parametry** nie zaznaczono opcji **Konto główne** jako wymiaru kontroli budżetu, ale określone wydatki podlegają zarządzaniu, można zaznaczyć te wydatki na karcie **Wybór konta głównego**. Jeśli opcja **Konto główne** jest zaznaczona jako wymiar kontroli budżetu, nie trzeba dodawać żadnych wpisów.  

### <a name="define-budget-groups"></a>Zdefiniuj grupy budżetu

Na karcie **Zdefiniuj grupy budżetu** opcjonalnie można zdefiniować unikatowe kombinacje wymiarów finansowych, gdzie zasoby budżetowe są grupowane na potrzeby pomocniczej kontroli budżetu. Można utworzyć jeden rekord zawierający całą organizację lub zdefiniować wiele grup dla poszczególnych działów lub centrów kosztów.  

### <a name="define-message-levels"></a>Definiowanie poziomów wiadomości

Jeśli komunikaty ostrzegawcze kontroli budżetu mają być pomijane dla dowolnej grupy użytkowników, można określić te grupy na stronie **Definiowanie poziomów wiadomości**. Członkowie grup użytkowników będą nadal otrzymywali komunikaty o błędach, gdy przekroczą dostępne środki budżetowe, na podstawie ich indywidualnych uprawnień przekraczania budżetu.

### <a name="activate-budget-control"></a>Uruchamianie kontroli budżetu

Po skonfigurowaniu kontroli budżetu można włączyć tę funkcję i ją uaktywnić na karcie **Uruchamianie kontroli budżetu**. Zacznie wtedy obowiązywać wersja robocza.
> [!Important]
> Po kontroli budżetu jest włączony i aktywny, a po zaksięgowaniu transakcji, nie powinny być zostało wyłączone w połowie roku. Jeśli kontrola budżetu jest wyłączona, działania nie są rejestrowane na potrzeby kontroli budżetu i operacje sprawdzania budżetu nie są już wykonywane. W związku z tym dokumenty, które już zostały zaksięgowane, mogą błędnie odzwierciedlać wszelkie zwalniające kwoty lub salda w zapytaniach i raportach powiązanych z kontrolą budżetu. Dotyczy to m.in. statystyk kontroli budżetu dla wszelkich dokumentów i arkuszy transakcji z jednostkami podrzędnymi i korygujących. 

Ponadto transakcje, w tym wpisy do rejestru budżetu, które zaksięgowano przed włączeniem kontroli budżetu, nie są uwzględniane w kontroli budżetu. Dlatego warto włączyć kontrolę budżetu tylko na początku nowego cyklu budżetu. Upewnij się, że wpisy do rejestru budżetu zawierające początkowe salda budżetu dla kontroli budżetu mają aktualizowane salda budżetu dopiero po włączeniu kontroli budżetu. Każdy otwarty dokument (np. zamówienie zakupu) będzie sprawdzany pod kątem dostępnych środków budżetowych i uzyska rezerwację budżetu dla kontroli budżetu, gdy użytkownik ręcznie uruchomi kontrolę budżetu w dokumencie.

## <a name="using-budget-control"></a>Korzystanie z kontroli budżetu
Po włączeniu kontroli budżetu użytkownicy otrzymają komunikaty ostrzeżeń i błędów kontroli budżetu w dokumentach i dziennikach skonfigurowanych dla kontroli budżetu. Należy pamiętać, że kontrolę budżetu można skonfigurować tak, aby użytkownicy byli ostrzegani, gdy przekroczą środki budżetowe, ale nadal mogli potwierdzić lub zaksięgować transakcję. Użytkownicy mogą wyświetlać szczegóły nieudanych operacji kontroli budżetu na stronie **Błędy i ostrzeżenia kontroli budżetu**.   

Z tej strony, użytkowników można wejść do **statystyki kontroli budżetu wg okresu** stronę do widoku Szczegóły dotyczące dostępności budżetu i rezerwacje dla kombinacji wymiarów budżetu wybranego formantu. Użytkownicy mogą również przejść do strony **Statystyka kontroli budżetu** w celu wyświetlenia dostępności budżetu dla wszystkich kombinacji wymiarów finansowych, które są używane w kontroli budżetu. 

Po włączeniu kontroli budżetu dla zamówień zakupu menedżer budżetu może w obszarze roboczym **Budżety i prognozy księgi** sprawdzić kolejkę wszystkich niepotwierdzonych zamówień zakupu, które mają ostrzeżenia i błędy kontroli budżetu. Jeśli menedżer budżetu ma skonfigurowane uprawnienia ponadbudżetowe, może potwierdzać zamówienia zakupu bezpośrednio w obszarze roboczym.    


