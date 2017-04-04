---
title: "Na podstawie działania podwykonawstwa"
description: "W tym temacie opisano szczegółowo, jak używać działań podwykonawczych w przepływie produkcji dla produkcji oszczędnej."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8e57c53ca894aa44b71e15c1f66bd7c722ea8a81
ms.lasthandoff: 03/31/2017


---

# <a name="activity-based-subcontracting"></a>Na podstawie działania podwykonawstwa

W tym temacie opisano szczegółowo, jak używać działań podwykonawczych w przepływie produkcji dla produkcji oszczędnej.

W Microsoft Dynamics 365 dla operacji, istnieją dwa podejścia do podwykonawstwa: zleceń produkcyjnych i lean manufacturing. W ujęciu od strony produkcji oszczędnej prac podwykonawczych jest modelowana jako usługa, która jest powiązana z działania przepływu produkcji. Specjalny typ typ grupy kosztów, o nazwie **outsourcingu bezpośredniego**, wprowadzono i usług podwykonawczych nie są już częścią zestawieniem komponentów (BOM). Rachunku kosztów prac podwykonawczych jest w pełni zintegrowany z rozwiązaniem wyceny dla produkcji oszczędnej.

## <a name="production-flows-that-involve-subcontractors"></a>Przepływów produkcji, które obejmują podwykonawców
Podstawową zasadą przepływu produkcji nie zmienia się podczas działania są wykonywane przez podwykonawców. Materiał nadal przepływa między lokalizacjami, czynności procesu konwersji materiału do produktów i działania związane z transferem przenieść materiałów lub produktów z jednej lokalizacji do drugiej. Można model lokalizacji i pracować komórki jako dostawcy zarządzanych do magazynu lub do zasobu, grupy zasobów, przypisując konta dostawcy.  

Oparte na tych możliwości, produkcji oszczędnej nie wymaga żadnych szczególnych funkcji w celu obsługi przepływu materiałów i produktów. Wszystkie możliwe scenariusze obejmujące dostawców dostawcy usług produkcji lub transportu mogą być modelowane oparty na architekturze przepływu produkcji i działań.  

Na przykład podwykonawcy działa z supermarketu, który jest umieszczony pod podwykonawcy. Jednostek obsługi są opróżniane w podwykonawcy, karty kanban są zwracane do zestawu komórki wraz z następną przesyłką. Następnie jest uzupełniany supermarketów o podwykonawcy. Transfer z podwykonawcą i mogą być modelowane jako transfer jawne działania zmierzające do wspierania pobrania i proces wysyłki. Jeśli jawnego rejestracji nie jest wymagane do obsługi transportu fizyczne, można pominąć działania związane z transferem.  

Podwykonawca może służyć do ogólnej zdolności przepływu produkcji równoważenia obciążenia. Na przykład przepływ produkcji jest modelowana przy użyciu reguł kanban zaplanowane. Terminarz używa planowania forum, aby zaplanować i poziom obciążenia kanban zarówno komórki robocze na żądanie. Terminarz również monitoruje harmonogram dostaw skonsolidowanych supermarkecie na **harmonogramu dostaw** strony. Wiele podwykonawców mogą być modelowane w jednej lub wielu przepływów produkcji i może być wiele reguł kanban, które mogą być używane do dostarczania tego samego produktu w tej samej lokalizacji, poprzez różne działania. Terminarz można przekonwertować kart Kanban do alternatywnej reguły kanban do harmonogramu kanban, który został pierwotnie utworzony dla wewnętrznej produkcji inny proces. W rzeczywistości podwykonawców charakter komórki roboczej nie ma wpływu na przepływ produkcji. Ta sama zasada pracy obowiązuje dla dwóch komórek równoległą pracę wewnętrznego lub dwie komórki podwykonawców.   

Jak inne działania w przepływie produkcji, działań podwykonawczych można wykorzystać i dostarczenie dodawanych, nieobjętych inwentaryzacją (Praca w toku \[PWT\]) oraz materiał półproduktów i produktów. We wszystkich przypadkach procesy planowania i wykonywania czynności objętych podzleceniami są takie same. Ponadto te proces taki sam, jak procesów wewnętrznych.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Proces zakupu dla działań podwykonawczych (usługi)
Procesu zakupu dla działań podwykonawczych opiera się na fizyczne przepływu materiału, który został zarejestrowany przez postępu zadań kanban, na przykład, uruchomić lub zakończyć. Finansowe przepływ, na przykład kosztów prac podwykonawczych jest dodatkowy przepływ, który następuje fizyczny przepływ. W tym samym czasie procesu zakupu jest to niezależny proces, który pozwala na ręczne dopasowanie dokumentów zakupu na każdym kroku. Oto proces zakupu dla działań podwykonawczych:

1.  Tworzenie umowy zakupu. Umowy zakupu jest tworzone dla usługi i podłączony do działania przepływu produkcji.
2.  Umożliwia tworzenie zamówienia zakupu. Zlecenia wydania zakupu mogą być tworzone dla usługi oparte na zadania według harmonogramu kanban. Zadania dla tej samej usługi mogą być grupowane do wierszy zamówienia zakupu według dnia, tygodnia lub miesiąca. Wiersze zamówienia zakupu mogą być tworzone w dowolnym momencie po utworzeniu zadania kanban. Wiersze zamówienia zakupu mogą być tworzone nawet po fakcie. Tę opcję zaznacza się zazwyczaj, jeżeli podwykonawca dostarcza usługi bez dodatkowego powiadomienia, opartych na kartach kanban i karty Kanban, które odbiera podwykonawcy. W takim przypadku można zminimalizować odchylenia między zamówienia zakupu i faktury.
3.  Generowanie kart kanban, materiałów i listy pobrania do wysyłania do podwykonawcy, aby przygotować się do przetwarzania. Oparty na szczegółowego modelowania przepływu produkcji, przygotowania odbywa się na tablicy kanban dla działania procesu przy użyciu listy pobrania i funkcja przygotowania. Alternatywnie przygotowanie odbywa się na tablicy Kanban dla zadań przeniesienia przy użyciu listy pobrania i rozpoczęcia lub zakończenia. Dla dodawanych materiału oba procesy mogą być obsługiwane przez WMS pobrania i proces wysyłki. Konosament mogą być tworzone na żądanie.
4.  Generowanie jednostki obsługi kanban i karty kanban. Po przetworzeniu, karty są zwracane z podwykonawcą. Zwykle karty obejmują dostawy, która określa fizyczne materiału, która została wysłana. Odwołanie do świadczonych usług nie jest wymagane. Przybycie materiału lub produktu u klienta jest zarejestrowany na tablicy Kanban, w zależności od kart kanban. (Kanban dla działania procesu lub tablicy kanban dla zadań przeniesienia jest używany, w zależności od działań modelowanych.).
5.  Utworzenia przyjęcia Doradczym. Przyjęcia Doradczy może służyć do zastąpienia pakowania dokumentu dostawy dla otrzymanej usługi. Wskazówki dotyczące przyjęcia mogą być generowane w oparciu zadań kanban ukończone działania podwykonawstwa w wybranym okresie. Dla każdego przyjęcie zadania klasyfikatory są tworzone dla wiersza zamówienia zakupu powiązanych. Doradczy przyjęcia może być drukowane i wysyłane do podwykonawcy jako potwierdzenie odbioru.
6.  Generowanie faktury.

Proces kończy się, gdy podwykonawca jest fakturowane na okres. Uwzględnij faktury jest wykonywane przed klasyfikatory przychodu, które zostały utworzone. Ponieważ klasyfikatory przyjęcia reprezentują dokładne fizyczny odbiór materiału, uzgadnianie trzyelementowe jest uproszczone.

## <a name="configuring-activities-for-subcontracting"></a>Konfigurowanie działania dotyczące podwykonawstwa
Poniżej opisano jak skonfigurować działania dotyczące podwykonawstwa.

### <a name="subcontracted-services"></a>Usług podwykonawczych

Płatności element, który jest używany w według działalności podwykonawstwa muszą być produktu, który ma następujące właściwości:

-   **Typ produktu:** usługi
-   **Grupy modeli magazynu:** nie są magazynowane

To wymaganie wymusza użycie pierwszym w pierwszym FIFO model magazynu. **Uwaga:** kalkulacji kosztu produktów wymaga zdefiniowania standardowy koszt usługi. Wymagana jest zgoda zakupu z dostawcą. W przeciwnym wypadku usługa nie może służyć do według działalności podwykonawstwa.

### <a name="subcontracted-process-activities"></a>Czynności procesu podwykonawców

Aby skonfigurować działania procesu jako działań podwykonawczych, wykonaj następujące kroki.

1.  Skonfiguruj komórki prac podwykonawczych. Aby skonfigurować komórki roboczej jako zlecona, należy utworzyć zasób z **dostawcy** wpisz i skojarzyć ją z komórki roboczej (grupę zasobów). Kategoria kosztu runtime z **outsourcingu bezpośredniego** typ grupy kosztów powinny być przypisane do komórki roboczej. Kategorie kosztów, Konfiguracja i ilość nie są wymagane.
2.  Po utworzeniu działania procesu i powiązana komórka robocza podwykonawców, należy skonfigurować usługi dla działania w celu aktywowania wersji przepływu produkcji. Po ukończeniu tego kroku na **aktywność****szczegóły** strony. Dla działań, które są skojarzone z komórką roboczą podwykonawców **warunki usługi** się skróconej. Na skróconej karcie dodać domyślną usługę, która jest prawidłowa dla wszystkich elementów danych wyjściowych. Jeśli elementy określonych danych wyjściowych wymagają różnych usług lub parametry obliczania różnych usług (na przykład stosunek innej usługi), można dodać inne usługi do działania.

## <a name="subcontracted-transfer-activities"></a>Działania związane z transferem podwykonawców
Działanie transferu jest skonfigurowany jako działanie podwykonawców, w zależności od **transportowane przez** ustawienie działanie transferu. Dostępne są następujące opcje:

-   **Dysponent ładunku** — działanie podwykonawcom, jeśli przeniesienie z magazynu jest zarządzany przez dostawcę (zgodnie z definicją właściwości magazynu). Wszystkie umowy zakupu wybranych usług musi mieć ten sam identyfikator dostawcy jako magazyn.
-   **Odbiorcy** — działanie podwykonawcom Jeśli przeniesienia do magazynu jest zarządzany przez dostawcę (zgodnie z definicją właściwości magazynu). Wszystkie umowy zakupu wybranych usług musi mieć ten sam identyfikator dostawcy jako magazyn.
-   **Przewoźnik** — działanie jest zlecona dowolnego dostawcy, który dostarcza usługę. Ważność, przewoźnik musi zostać utworzony dla zarządzania magazynem i musi mieć konto dostawcy przypisane.

Jeśli chodzi o działania procesu należy skonfigurować domyślną usługę do działania związane z transferem podwykonawców na **warunki usługi** skróconej **aktywność****szczegóły** strony.

## <a name="service-quantity-calculation"></a>Obliczanie ilości usługi
Proces zakupu całego opiera się na odwołanie do elementu dla usługi. To odwołanie do elementu jest mierzona w jednostkach miary usługi. Usługi są zwykle mierzone liczbę usług (jednostki) lub w czasie. Aby obliczyć ilość usług, oparte na zarejestrowanych ukończenie zadań w systemie kanban, można użyć następujących metod:

-   **Obliczenia, które opiera się na liczbę miejsc pracy** — jedno zadanie kanban jest równa *n* jednostek usługi, bez względu na ilość produktu, która jest dostarczana. W produkcji oszczędnej jedno zadanie odpowiada jednej jednostki obsługi. Metoda obliczania stosuje się do wszystkich usług, które mają stałe ceny za jednostkę obsługi. Dlatego ta metoda zazwyczaj stosuje się do działań przeniesienia. Jednakże można także zastosować do działań związanych z procesami, które przetwarzają jednostek obsługi całego.
-   **Obliczenia, które opiera się na ilość produktu** – ilości usługi jest względem ilość produktu, która jest zaplanowana dostarczone. Podczas obliczania ilości dostarczonego produktu, ilości błędów może być albo dołączone lub wykluczone. Metoda obliczania stosuje się do wszystkich przypadków, gdzie jest uzgodnione ceny serwisu na jednostkę produktu przetworzonego.
-   **Obliczenia, które opiera się na czas działania** – czasy działania teoretyczne są obliczane na podstawie czasu przetwarzania działania, Suma przetworzonych ilości i wskaźnik produktywności przetworzonego produktu. Metoda obliczania stosuje się do usług, które zostały zapłacone za godzinę i wariancji w czasie każdego produktu przetworzonego.

## <a name="cost-accounting-of-subcontracted-services"></a>Rachunek kosztów usług podwykonawczych
Po zaksięgowaniu przyjęcia Doradczym lub dostawca dostawy na zamówieniu zakupu, które zostały utworzone dla przepływu produkcji (innymi słowy, zamówienie zakupu, który został wygenerowany na podstawie zadań w systemie kanban dla działań podwykonawczych), wartość przyjęcia należy rozliczać w kontach PWT przepływu produkcji. Odchylenia faktur księguje się również do przepływu produkcji. Kategoria kosztu dla prac podwykonawczych został wprowadzony. Ta kategoria kosztu włączyć śledzenie przezroczyste wartości prac podwykonawczych, które jest przydzielany do PWT i zużytego w ciągu okresu.  

Wyceny dla lean manufacturing na koniec okresu wyceny wstecznej oblicza rzeczywisty odchylenia produktów, które są produkowane z przepływu produkcji w okresie wyceny.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Transfery modelowania jako działań podwykonawczych
Osoby często należy wziąć pod uwagę nieproduktywnych transportu i uważasz, że dodaje wartość nie. Jednakże gdy koszty podwykonawstwa jest porównywana do kosztu produkcji wewnętrznej, należy rozważyć kosztów transportu dodatkowych działań. Przepływ produkcji, który obejmuje wiele lokalizacji i wymaga usług transportowych powinny modelu kosztów transportu w ramach kosztów dostawy produktów do klienta. 

Według działalności podwykonawstwo produkcji oszczędnej pozwala zintegrować przewoźników i transportu dostawców, które przenoszą materiał i produktów między lokalizacjami przepływu produkcji. Za pomocą modelowania działanie transferu, można przypisać przewoźnika lub dostawcy. Działania/zadania przeniesienia opiera się na umowę sprzedaży, usług i można tworzyć zamówienia zakupu i wskazówki dotyczące przyjęcia, oparte na zadania rzeczywistego przeniesienia. Ta funkcja jest taka sama, jak funkcje dla działań podwykonawczych procesu.  

W związku z tym Dynamics 365 dla operacji teraz obsługuje Obliczanie BOM, zawierający usług transportowych, tworzenie powiązanych zamówień zakupu, przyjęcie zintegrowane rejestracji i integracji transportu usługi kosztów do wyceny przepływu produkcji.


