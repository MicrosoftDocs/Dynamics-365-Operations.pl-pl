---
title: "przepływ pracy zapotrzebowań zakupu"
description: "Przepływ pracy prowadzi zapotrzebowanie na zakup przez proces weryfikacji — od początkowego stanu Wersja robocza do końcowego Zatwierdzone. Gdy zapotrzebowanie na zakup zostanie przesłane do przeglądu, rozpoczyna się proces przepływu pracy. Po zatwierdzeniu zapotrzebowania na zakup można wygenerować zamówienie zakupu dla wierszy zapotrzebowania na zakup i przesłać do dostawcy w celu realizacji zamówienia."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchReqAuthorization, WorkflowParticipantExpenToken
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2234
ms.assetid: dad3ba5a-2892-45d2-874a-300896f59b34
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 95d1d3a34728aab38f77635ae68bea16b08f6587
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---

# <a name="purchase-requisition-workflow"></a>przepływ pracy zapotrzebowań zakupu

[!include[banner](../includes/banner.md)]


Przepływ pracy prowadzi zapotrzebowanie na zakup przez proces weryfikacji — od początkowego stanu Wersja robocza do końcowego Zatwierdzone. Gdy zapotrzebowanie na zakup zostanie przesłane do przeglądu, rozpoczyna się proces przepływu pracy. Po zatwierdzeniu zapotrzebowania na zakup można wygenerować zamówienie zakupu dla wierszy zapotrzebowania na zakup i przesłać do dostawcy w celu realizacji zamówienia.

Przed przesłaniem zapotrzebowania zakupu do przeglądu należy skonfigurować przepływ pracy. Proces przepływu pracy może zawierać jeden lub więcej kroków przeglądu o dowolnej kolejności. Proces przepływu pracy można również konfigurować tak, aby pominąć zadania przeglądu i automatyczne zatwierdzać zapotrzebowania na zakup. Można skonfigurować przepływ pracy, tak aby przekazywać zapotrzebowanie na zakup jako pojedynczy dokument lub przekazywać pojedyncze wiersze zapotrzebowania na zakup do odpowiednich osób sprawdzających. Oprócz tego można utworzyć scenariusz, w którym zapotrzebowanie na zakup jest kierowane jako pojedynczy dokument do niektórych osób sprawdzających, a do innych są kierowane wybrane wiersze zapotrzebowania na zakup.  

Jeśli wiersze zapotrzebowania na zakup są przeglądane indywidualnie, proces przeglądu musi zostać ukończony dla wszystkich wierszy, zanim przepływ pracy będzie mógł przejść do następnego kroku procesu i zanim będzie można zakończyć cały proces przeglądu zapotrzebowania na zakup. Gdy proces przeglądu zapotrzebowania na zakup (ze wszystkimi jego wierszami) zostanie zakończony, ogólny status zapotrzebowania na zakup zmieni się na **Zatwierdzono**.  

Przepływ pracy można tak skonfigurować, aby odpowiadał obowiązującemu w danej organizacji procesowi biznesowemu związanemu z zapotrzebowaniami na zakup. Podczas konfigurowania procesu przepływu pracy zapotrzebowania na zakup należy rozważyć poniższe kwestie:

-   Jakie rozchody muszą podlegać przeglądowi?
-   Jakie rozchody można zatwierdzać automatycznie?
-   Kto musi przeglądać i zatwierdzać wnioski dotyczące rozchodów? Jaką rolę przypisano tym użytkownikom?
-   Jaki proces musi zostać wykonany, jeśli osoba sprawdzająca nie jest dostępna?

Poniższe przykłady ilustrują dwie konfiguracje przepływu pracy dla zapotrzebowań na zakup.

## <a name="example-1-route-a-purchase-requisition-as-a-single-document-for-review"></a>Przykład 1: Kierowanie zapotrzebowania na zakup jako pojedynczego dokumentu do przeglądu
Na poniższej ilustracji pokazano przykładową drogę zapotrzebowania na zakup traktowanego jako pojedynczy dokument w procesie przepływu pracy. Wiersze w zapotrzebowaniu na zakup nie są kierowane pojedynczo. W tym przykładzie w procesie przepływu pracy uwzględniono następujące role:

-   **Zleceniodawca** — użytkownik, który zgłasza zapotrzebowanie na towary lub usługi. Zapotrzebowanie na zakup może przygotować zleceniodawca lub inny pracownik w jego imieniu. Ten pracownik jest wystawcą. Wystawca odpowiada za zarządzanie zapotrzebowaniem na zakup w całym procesie przeglądu. Zapotrzebowanie na zakup może zmodyfikować tylko wystawca.

**Uwaga:** Aby pracownik mógł utworzyć zapotrzebowanie na zakup w imieniu innej osoby, należy mu przyznać odpowiednie uprawnienia. Użyj strony **uprawnienia zapotrzebowania na zakup** do konfigurowania tych uprawnień.

-   **Pracownik działu zakupów** — użytkownik, który dokonuje przeglądu zamówienia i może zatwierdzić dokument.
-   **Menedżer zleceniodawcy** — użytkownik, który dokonuje przeglądu menedżerskiego i może zatwierdzić dokument.

![Przepływ pracy w procesie przeglądu zapotrzebowania na zakup](./media/purchreqworkflowoverview_submission.gif)  
W tym przykładzie proces przepływu pracy dla zamówienia na zakup obejmuje następujące kroki:

1.  Wystawca przesyła zapotrzebowanie na zakup do przeglądu.
2.  Pracownik działu zakupów odbiera powiadomienie. Powiadomienie zawiera wniosek o sprawdzenie informacji w zapotrzebowaniu na zakup. Jeśli będzie brakowało wymaganych informacji, pracownik działu zakupów może je dodać albo zwrócić zapotrzebowanie na zakup do wystawcy w celu uzupełnienia. Po podaniu wszystkich wymaganych informacji zapotrzebowanie na zakup może zostać przekazane do następnego kroku w procesie przeglądu.
3.  Kierownik zleceniodawcy sprawdza zapotrzebowanie na zakup. Zapotrzebowanie na zakup może zostać skierowane do menedżera zleceniodawcy, jeśli na przykład kwota zapotrzebowania na zakup przekracza limit wydatków zlecającego związanych z zapotrzebowaniami na zakup. Menedżer zleceniodawcy może zatwierdzić lub odrzucić zapotrzebowanie na zakup albo zwrócić je wystawcy w celu wprowadzenia zmian.

## <a name="example-2-route-the-individual-purchase-requisition-lines-for-review"></a>Przykład 2: Kierowanie poszczególnych wierszy zapotrzebowania na zakup do przeglądu
Na poniższej ilustracji pokazano drogę pojedynczych wierszy zapotrzebowania na zakup w przepływie pracy. Proces dla każdego wiersza jest ogólnie taki sam jak proces dla zapotrzebowania na zakup kierowanego do przeglądu jako pojedynczy dokument. Niemniej, każdy wiersz musi przejść proces przepływu pracy osobno, zanim przepływ pracy dla zapotrzebowania na zakup jako całości będzie mógł zostać zakończony.  

W tym przykładzie pracownik wprowadza wniosek o zakup plakatów i koszulek na potrzeby kampanii marketingowej. Kosz plakatów jest dzielony między działy marketingu i sprzedaży. Jeśli koszt plakatów lub koszulek przekracza limit podpisywania kierowników działu, zapotrzebowanie na zakup musi zostać przejrzane również przez menedżera grupy.  

W tym przykładzie w procesie przepływu pracy uwzględniono następujące role:

-   **Zleceniodawca** — użytkownik, który zgłasza zapotrzebowanie na towary lub usługi. Zapotrzebowanie na zakup może przygotować zleceniodawca lub inny pracownik w jego imieniu. Ten pracownik jest wystawcą. Wystawca odpowiada za zarządzanie zapotrzebowaniem na zakup w całym procesie przeglądu. Zapotrzebowanie na zakup może zmodyfikować tylko wystawca.

**Uwaga:** Aby pracownik mógł utworzyć zapotrzebowanie na zakup w imieniu innej osoby, należy mu przyznać odpowiednie uprawnienia. Użyj strony **uprawnienia zapotrzebowania na zakup** do konfigurowania tych uprawnień.

-   **Pracownik działu zakupów** — użytkownik, który dokonuje przeglądu zamówienia i może zatwierdzić dokument.
-   **Menedżer zleceniodawcy** — użytkownik, który dokonuje przeglądu menedżerskiego i może zatwierdzić dokument.
-   **Menedżer działu** — użytkownik, który dokonuje przeglądu rozchodu i może zatwierdzić dokument.
-   **Menedżer grupy** — użytkownik, który dokonuje przeglądu związanego z autoryzacją podpisu i może zatwierdzić dokument.

![Przepływ pracy w procesie przeglądu wiersza zapotrzebowania na zakup](./media/purchreqlineworkflowoverview.gif)  
W tym przykładzie proces przepływu pracy dla wierszy zamówienia na zakup obejmuje następujące kroki:

1.  Wystawca przesyła zapotrzebowanie na zakup do przeglądu. Każdy wiersz jest kierowany do osoby sprawdzającej, która w procesie przepływu pracy otrzymała uprawnienia do pobierania go.
2.  Pracownik działu zakupów odbiera powiadomienie. Powiadomienie z wnioskiem o sprawdzenie informacji w zapotrzebowaniu na zakup i w jego wierszach. Gdy zapotrzebowanie na zakup zostanie otwarte przez pracownika działu zakupów, wszystkie wiersze są widoczne, ale wizualny wskaźnik informuje, które wiersze zostały wysłane pracownikowi do zweryfikowania. Jeśli będzie brakowało wymaganych informacji, pracownik działu zakupów może je dodać albo zwrócić wiersz zapotrzebowania na zakup do wystawcy w celu uzupełnienia. Po podaniu wszystkich wymaganych informacji wiersz zapotrzebowania na zakup może zostać przekazane do następnego kroku w procesie przeglądu. Wiersze zapotrzebowania na zakup mogą być przekazywane dalej w procesie przeglądu niezależnie od siebie nawzajem.
3.  Kierownik linii zleceniodawcy sprawdza i zatwierdza wiersze zapotrzebowania na zakup. Zatwierdzenie może zostać skierowane do menedżera zleceniodawcy, jeśli na przykład kwota wiersza zapotrzebowania na zakup przekracza limit wydatków zlecającego związanych z wierszami zapotrzebowania na zakup. Menedżer można zatwierdzić lub odrzucić jeden lub oba wiersze zapotrzebowania na zakup.
4.  Menedżer działu marketingu sprawdza wiersze zapotrzebowania na zakup dotyczące plakatów i koszulek. Menedżer działu sprzedaży sprawdza tylko te wiersze zapotrzebowania na zakup, które dotyczą plakatów, ponieważ jest to jedyny koszt, za który odpowiada dział sprzedaży.
5.  Menedżer grupy przegląda i zatwierdza wiersz zapotrzebowania na zakup koszulek tylko wtedy, gdy wymagana jest zgoda menedżera grupy, np. gdy kwota wiersza zapotrzebowania na zakup przekracza limit zatwierdzania kierownika działu. Menedżer grupy nie musi zatwierdzać wiersza zapotrzebowania na zakup plakatów.

## <a name="configuring-a-workflow-for-purchase-requisitions"></a>Konfigurowanie przepływu pracy dla zapotrzebowań na zakup
Aby skierować zapotrzebowanie na zakup do przeglądu, należy skonfigurować procesy przepływu pracy zapotrzebowania na zakup. Definiowany proces przepływu pracy kontroluje interakcje między użytkownikiem, który zgłosił zapotrzebowanie na pozycje (zleceniodawca), a osobami sprawdzającą i zatwierdzającą w przepływie pracy. Kierowanie zapotrzebowania na zakup zależy od warunków, które są określone w konfiguracji przepływu pracy. Na przykład warunki te mogą określać, kiedy zapotrzebowanie na zakup ma być kierowane, użytkownika lub rolę, do której zapotrzebowanie na zakup ma być kierowane oraz działania, które użytkownik może podjąć.  

W przykładach zawartych w tym temacie opisano możliwy sposób kierowania zamówienia na zakup w przepływie pracy jako pojedynczego dokumentu lub jako osobnych wierszy zapotrzebowania na zakup. Można także skonfigurować przepływ pracy dla zapotrzebowań na zakup w celu odzwierciedlenia przeglądu kontroli wewnętrznej zapotrzebowań na zakup zdefiniowanego dla danej organizacji.  

Uczestnicy lub osoby sprawdzające, do których jest przypisane zadanie w przepływie pracy, mogą być członkami określonej grupy użytkowników, użytkownikami mającymi określone role zabezpieczeń, użytkownikami skojarzonymi z przesyłającym ofertę w hierarchii menedżerskiej, lub nazwanymi użytkownikami o określonych obowiązkach związanych z wydatkami.

### <a name="purchase-requisition-expenditure-reviewers"></a>Osoby sprawdzające wydatki związane z zapotrzebowaniami na zakup

Można tworzyć konfiguracje rewidenta rozchodów na potrzeby dynamicznych marszrut rozchodów dla przeglądu w oparciu o użytkownika przypisanego do roli projektu lub wymiar finansowy, w którym rozchód jest naliczany. Proces przepływu pracy korzysta z określonej roli projektu lub właściciela wymiaru finansowego przy ustalaniu celu marszruty rozchodu.  

Można zdefiniować jedną lub więcej konfiguracji rewidenta rozchodów, a następnie wybrać konfigurację podczas tworzenia przepływu pracy. Można konfigurować wartości rewidenta rozchodów dla każdej firmy w organizacji. Zdefiniowane konfiguracje rewidenta rozchodów są przypisywane do zadań przepływu pracy.  

Tworzenie konfiguracji rewidenta rozchodów nie jest konieczne. Istnieje możliwość przypisywania konkretnego użytkownika lub grupy użytkowników jako rewidenci podczas definiowania przepływu pracy. Jednak w przypadku złożonej organizacji określanie rewidentów rozchodów może zwiększyć wydajność procesu zatwierdzania. Ponadto w przypadku ustawienia osób sprawdzających wydatki, nie trzeba aktualizować przypisań osoby sprawdzającej w przepływie pracy za każdym razem, gdy osoba sprawdzająca zmienia role w zadaniu.  

Osoby sprawdzające wydatki można skonfigurować na stronie **Osoby sprawdzające wydatki związane z zapotrzebowaniami na zakup**. Utwórz konfigurację rewidenta rozchodów i wprowadź wartości dla każdej firmy określonej dla danej organizacji. Dla zapotrzebowań, które są przypisane do projektu można określić rolę odpowiedzialną za przegląd zapotrzebowania w: Kontroler projektu, Menedżer projektu lub Menedżer sprzedaży projektu. Rozchody będą wysyłane do użytkownika, który zostanie przypisany do określonej roli. Można także kierować rozchód do właściciela wymiaru finansowego, zaznaczając odpowiednie pole wyboru wymiaru finansowego na karcie **Dystrybucje organizacji**.  

Aby skorzystać z jednej z osób sprawdzających wydatki, które zostały skonfigurowane w przepływie pracy, należy ustawić opcję **Typ uczestnika** jako **Uczestnicy rozchodu** we właściwościach **przypisania** dla odpowiedniego elementu przepływu pracy.

<a name="see-also"></a>Informacje dodatkowe
--------

[Tworzenie zapotrzebowania na zużycie (przewodnik po zadaniu)](/dynamics365/unified-operations/supply-chain/procurement/tasks/create-requisition-consumption)

[Definiowanie przepływów pracy procesów biznesowych dla zapotrzebowań na zakup](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

[Przepływy pracy dla zaopatrzenia i sourcingu](procurement-sourcing-workflows.md)

[Omówienie zapotrzebowania na zakup](purchase-requisitions-overview.md)




