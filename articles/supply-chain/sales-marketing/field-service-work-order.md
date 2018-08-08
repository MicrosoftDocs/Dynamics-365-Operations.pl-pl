---
title: "Synchronizowanie zleceń pracy w aplikacji Field Service ze zleceniami pracy w aplikacji Finance and Operations"
description: "W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania zleceń pracy w aplikacji Field Service ze zleceniami pracy w aplikacji Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 8914723f6ef436bfc9e3a98cc82d5486042b0761
ms.openlocfilehash: 250b7caa1e1495140d0d4f688ecae4acb8814467
ms.contentlocale: pl-pl
ms.lasthandoff: 06/07/2018

---

# <a name="synchronize-work-orders-in-field-service-to-sales-orders-in-finance-and-operations"></a>Synchronizowanie zleceń pracy w aplikacji Field Service ze zleceniami pracy w aplikacji Finance and Operations

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania zleceń pracy w programie Microsoft Dynamics 365 for Field Service ze zleceniami pracy w programie Microsoft Dynamics 365 for Finance and Operations.

[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)

W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania zleceń pracy w aplikacji Field Service ze zleceniami pracy w aplikacji Finance and Operations.

## <a name="templates-and-tasks"></a>Szablony i zadania

Następujące szablony i podstawowe zadania są używane do wykonywania synchronizacji zleceń pracy w aplikacji Field Service ze zleceniami pracy w aplikacji Finance and Operations.

### <a name="names-of-the-templates-in-data-integration"></a>Nazwy szablonów w integracji danych

Do wykonywania synchronizacji służy szablon **Zlecenia pracy na zamówienia sprzedaży (z Field Service do Fin and Ops)** .

### <a name="names-of-the-tasks-in-the-data-integration-project"></a>Nazwy zadań w projekcie integracji danych

- WorkOrderHeader
- WorkOrderServiceLineEstimate
- WorkOrderServiceLineUsed
- WorkOrderProductLineEstimate
- WorkOrderProductLineUsed

Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować nagłówki i wiersze zamówień sprzedaży:

- Produkty programu Field Service (z Fin and Ops do Field Service)
- Produkty (z Sales do Fin and Ops) — bezpośrednie

## <a name="entity-set"></a>Zestaw jednostek

| **Field Service** | **Finance and Operations** |
|-------------------------|-------------------------|
| msdyn_workorders        | Nagłówki zamówień sprzedaży CDS |
| msdyn_workorderservices | Wiersze zamówienia sprzedaży CDS   |
| msdyn_workorderproducts | Wiersze zamówienia sprzedaży CDS   |

## <a name="entity-flow"></a>Przepływ jednostek

Zlecenia pracy są tworzone w aplikacji Field Service. Jeśli zlecenia pracy zawierają tylko zewnętrznie obsługiwane produkty, a wartość w polu **Stan zlecenia pracy** różni się od wartości w polach **Otwarte — niezaplanowane** i **Zamknięte — anulowane**, zlecenia pracy mogą być synchronizowane z aplikacją Finance and Operations za pośrednictwem projektu integracji danych z usługą CDS. Aktualizacje w zleceniach pracy będą synchronizowane jako zamówienia sprzedaży w programie Finance and Operations. Do tych aktualizacji należą informacje o typie źródła i stanie.

## <a name="estimated-versus-used"></a>Szacowane a używane

W aplikacji Field Service produkty i usługi w zleceniach pracy mają dla ilości i kwot zarówno wartości **Oszacowany**, jak i **Użyte**. Jednak w aplikacji Finance and Operations zamówienia sprzedaży nie bazują na takiej koncepcji wartości **Oszacowany** i **Użyte**. Aby umożliwić alokację produktów, która korzysta z ilości oczekiwanej z zamówienia sprzedaży w aplikacji Finanse Finance and Operations, ale zachować ilość użytą, która ma być zużywana i fakturowana, dwa zestawy zadań synchronizują produkty i usługi w zleceniu pracy. Jeden zestaw zadań dotyczy wartości **Oszacowany**, a drugi zestaw zadań jest dla wartości **Użyte**.

To zachowanie umożliwia scenariusze, gdzie wartości szacowane są stosowane do alokacji lub rezerwacji w programie Finance and Operations, a wartości użyte są stosowane do zużycia i fakturowania.

### <a name="estimated"></a>Oszacowany

W synchronizacji wierszy produktów wartości **Oszacowany** są stosowane, gdy opcja **Stan wiersza** ma wartość **Oszacowany**, opcja **Alokowane** ma wartość **Tak**, a opcja **Stan systemu** nie ma wartości **Zamknięte — zaksięgowane**.

W synchronizacji wierszy usług wartości **Oszacowany** są stosowane, gdy opcja **Stan wiersza** ma wartość **Oszacowany**, a opcja **Stan systemu** nie ma wartości **Zamknięte — zaksięgowane**.

### <a name="used"></a>Użyte

Wartości **Użyte** są stosowane do zużycia i fakturowania. W takich przypadkach wartości **Użyte** są synchronizowane.

Poniższa tabela zawiera przegląd różnych kombinacji dla wierszy produktów.

| Stan systemu <br>(Field Service) | Stan wiersza <br>(Field Service) | Alokowane <br>(Field Service) |Zsynchronizowana wartość <br>(Finance and Operations) |
|--------------------|-------------|-----------|---------------------------------|
| Otwarte — zaplanowane   | Oszacowany   | Tak       | Oszacowany                       |
| Otwarte — zaplanowane   | Oszacowany   | Nr        | Użyte                            |
| Otwarte — zaplanowane   | Użyte        | Tak       | Użyte                            |
| Otwarte — zaplanowane   | Użyte        | Nr        | Użyte                            |
| Otwarte — w toku | Oszacowany   | Tak       | Oszacowany                       |
| Otwarte — w toku | Oszacowany   | Nr        | Użyte                            |
| Otwarte — w toku | Użyte        | Tak       | Użyte                            |
| Otwarte — w toku | Użyte        | Nr        | Użyte                            |
| Otwarte — zakończone   | Oszacowany   | Tak       | Oszacowany                       |
| Otwarte — zakończone   | Oszacowany   | Nr        | Użyte                            |
| Otwarte — zakończone   | Użyte        | Tak       | Użyte                            |
| Otwarte — zakończone   | Użyte        | Nr        | Użyte                            |
| Zamknięte — zaksięgowane    | Oszacowany   | Tak       | Użyte                            |
| Zamknięte — zaksięgowane    | Oszacowany   | Nr        | Użyte                            |
| Zamknięte — zaksięgowane    | Użyte        | Tak       | Użyte                            |
| Zamknięte — zaksięgowane    | Użyte        | Nr        | Użyte                            |

Poniższa tabela zawiera przegląd różnych kombinacji dla wierszy usług.

| Stan systemu <br>(Field Service) | Stan wiersza <br>(Field Service) | Zsynchronizowana wartość <br>(Finance and Operations) |
|--------------------|-------------|-----------|
| Otwarte — zaplanowane   | Oszacowany   | Oszacowany |
| Otwarte — zaplanowane   | Użyte        | Użyte      |
| Otwarte — w toku | Oszacowany   | Oszacowany |
| Otwarte — w toku | Użyte        | Użyte      |
| Otwarte — zakończone   | Oszacowany   | Oszacowany |
| Otwarte — zakończone   | Użyte        | Użyte      |
| Zamknięte — zaksięgowane    | Oszacowany   | Użyte      |
| Zamknięte — zaksięgowane    | Użyte        | Użyte      |

Synchronizacja wartości **Oszacowany** z wartościami **Użyte** jest zarządzana za pomocą dwóch zestawów zadań dla wierszy produktów i wierszy usług. Wstępnie zdefiniowane filtry wyzwalają poprawne zadanie, a bazowe mapowanie pomaga zagwarantować synchronizowanie poprawnych wartości **Oczekiwany** i **Użyte**.

### <a name="example"></a>Przykład

1. Zlecenie pracy jest tworzone i planowane w programie Field Service.

    Opcja **Stan systemu** ma wartość **Otwarte — zaplanowane**.

    - **Wiersz produktu:** Szacowana ilość = 5 szt., Użyta ilość = 0 szt., Stan wiersza = Oszacowany, Alokowane = Nie
    - **Wiersz usługi:** Szacowana ilość = 2 h, Użyta ilość = 0 h, Stan wiersza = Oszacowany

    W tym przykładzie z programem Finance and Operations jest synchronizowane ustawienie **Użyta ilość** o wartości **0** (zero) dotyczące produktu oraz ustawienie **Szacowana ilość** o wartości **2 h** dotyczące usługi.

2. Produkty są przydzielane w aplikacji Field Service.

    Opcja **Stan systemu** ma wartość **Otwarte — zaplanowane**.

    - **Wiersz produktu:** Szacowana ilość = 5 szt., Użyta ilość = 0 szt., Stan wiersza = Oszacowany, Alokowane = Tak
    - **Wiersz usługi:** Szacowana ilość = 2 h, Użyta ilość = 0 h, Stan wiersza = Oszacowany

    W tym przykładzie z programem Finance and Operations jest synchronizowane ustawienie **Szacowana ilość** o wartości **5 szt.** dotyczące produktu oraz ustawienie **Szacowana ilość** o wartości **2 h** dotyczące usługi.

3. Serwisant zaczyna pracować nad zleceniem pracy i rejestruje zużycie materiału w ilości 6.

    Opcja **Stan systemu** ma wartość **Otwarte — w toku**.

    - **Wiersz produktu:** Szacowana ilość = 5 szt., Użyta ilość = 6 szt., Stan wiersza = Użyte, Alokowane = Tak
    - **Wiersz usługi:** Szacowana ilość = 2 h, Użyta ilość = 0 h, Stan wiersza = Oszacowany

    W tym przykładzie z programem Finance and Operations jest synchronizowane ustawienie **Użyta ilość** o wartości **6** dotyczące produktu oraz ustawienie **Szacowana ilość** o wartości **2 h** dotyczące usługi.

4. Serwisant finalizuje zlecenie pracy i rejestruje użyty czas 1,5 godziny.

    Opcja **Stan systemu** ma wartość **Otwarte — zakończone**.

    - **Wiersz produktu:** Szacowana ilość = 5 szt., Użyta ilość = 6 szt., Stan wiersza = Użyte, Alokowane = Tak
    - **Wiersz usługi:** Szacowana ilość = 2 h, Użyta ilość = 1,5 h, Stan wiersza = Użyte

    W tym przykładzie z programem Finance and Operations jest synchronizowane ustawienie **Użyta ilość** o wartości **6** dotyczące produktu oraz ustawienie **Użyta ilość** o wartości **1,5 h** dotyczące usługi.

## <a name="sales-order-origin-and-status"></a>Źródło i stan zamówienia sprzedaży

### <a name="sales-origin"></a>Pochodzenie sprzedaży

Aby w programie Finance and Operations śledzić zamówienia sprzedaży pochodzące ze zleceń pracy, można utworzyć pochodzenie sprzedaży, w którym opcja gdzie **Przypisanie typu pochodzenia** ma wartość **Tak**, a w polu **Typ pochodzenia sprzedaży** ustawiono wartość **Integracja zlecenia**.

Domyślnie mapowanie wybiera pochodzenie sprzedaży o typie pochodzenia **Integracja zlecenia** dla wszystkich zamówień sprzedaży tworzonych na podstawie zleceń pracy. To zachowanie może być przydatne, gdy pracujesz z zamówieniami sprzedaży w programie Finance and Operations. Należy się upewnić, że zamówienia sprzedaży pochodzące ze zleceń pracy nie są synchronizowane z powrotem z programem Field Service jako zlecenia pracy.

Aby uzyskać szczegółowe informacje o prawidłowym konfigurowaniu pochodzenia sprzedaży w aplikacji Finance and Operations, zobacz rozdział „Warunki wstępne i ustawienia mapowania” w tym temacie.

### <a name="status"></a>Stan

Jeśli zamówienie sprzedaży pochodzi ze zlecenia pracy, na karcie **Ustawienia** w nagłówku zamówienia sprzedaży znajduje się pole **Zewnętrzny stan zlecenia**. To pole pokazuje systemowy stan ze zlecenia pracy w programie Field Service, aby ułatwić śledzenie stanu zlecenia pracy zsynchronizowanego z zamówieniem sprzedaży w programie Finance and Operations. To pole może również pomagać użytkownikowi programu Finance and Operations określić, kiedy zamówienie sprzedaży powinno zostać wysłane lub zafakturowane.

Pole **Zewnętrzny stan zlecenia** pole może przyjmować następujące wartości:

- Otwarte — zaplanowane
- Otwarte — w toku
- Otwarte — zakończone
- Zamknięte — zaksięgowane

## <a name="field-service-crm-solution"></a>Rozwiązanie CRM Field Service

Aby umożliwić integrację między programami Field Service i Finance and Operations, jest wymagana dodatkowa funkcjonalność z rozwiązania CRM Field Service. To rozwiązanie obejmuje następujące zmiany.

### <a name="work-order-entity"></a>Jednostka Zlecenie pracy

Do jednostki **Zlecenie pracy** dodano pole **Zawiera tylko zewnętrznie obsługiwane produkty** i ono jest wyświetlane na stronie. Jest ono używane do regularnego sprawdzania, czy zlecenie pracy zawiera wyłącznie produkty obsługiwane zewnętrznie. Zlecenie pracy zawiera tylko zewnętrznie obsługiwane produkty, jeżeli wszystkie odnośne produkty są obsługiwane w programie Finance and Operations. To ple pomaga zagwarantować, że użytkownicy nie będą synchronizowali zleceń pracy z produktami nieznanymi rozwiązaniu Finance and Operations.

### <a name="work-order-product-entity"></a>Jednostka Produkt zlecenia pracy

- Do jednostki **Produkt zlecenia pracy** dodano pole **Zamówienie zawiera tylko zewnętrznie obsługiwane produkty** i ono jest wyświetlane na stronie. Jest ono używane do regularnego sprawdzania, czy produkt zlecenia pracy jest zarządzany w programie Finance and Operations. To ple pomaga zagwarantować, że użytkownicy nie będą synchronizowali produktów zleceń pracy nieznanych rozwiązaniu Finance and Operations.
- Do jednostki **Produkt zlecenia pracy** dodano pole **Stan systemowy w nagłówku** i ono jest wyświetlane na stronie. Jest ono używane do regularnego sprawdzania systemowego stanu zlecenia pracy i pomaga zagwarantować poprawne filtrowanie, gdy produkty zlecenia pracy są synchronizowane z programem Finance and Operations. Gdy filtry zostaną ustawione w zadaniach integracji, informacja z pola **Stan systemowy w nagłówku** jest także używana do określenia, czy mają być synchronizowane wartości szacowane, czy używane.
- Pole **Zafakturowana kwota jednostkowa** zawiera kwotę, która została zafakturowana za faktycznie użytą jednostkę. Wartość jest obliczana przez podzielenie wartości z pola **Łączna kwota** przez wartość w polu **Ilość rzeczywista**. Pole jest używane do integracji z systemami, które nie obsługują różnych wartości ilości użytej i ilości zafakturowanej. To pole nie jest wyświetlane w interfejsie użytkownika (UI). 
- Wartość w polu **Zafakturowana kwota rabatu** jest obliczana jako wartość **Kwota rabatu** powiększona o zaokrąglenie z obliczania wartości **Zafakturowana kwota jednostkowa**. To pole jest używane do integracji i nie jest wyświetlane w interfejsie użytkownika.
- Pole **Ilość dziesiętna** przechowuje wartość z pola **Ilość** w postaci liczby dziesiętnej. To pole jest używane do integracji i nie jest wyświetlane w interfejsie użytkownika. 
- Wartość w polach **Użyte** jest resetowana na **0** (zero), jeśli w produkcie zlecenia pracy wartość w polu **Stan wiersza** zostanie zmieniona z **Użyte** na **Oszacowany**. Ta zmiana pomaga zapobiec sytuacjom, gdy ilość użyta wprowadzona przez pomyłkę zostanie wykorzystana w synchronizacji, jeżeli pole **Stan wiersza** ma wartość **Oszacowany**, a opcja **Alokowane** ma wartość **Nie**.

### <a name="work-order-service-entity"></a>Jednostka Usługa zlecenia pracy

- Do jednostki **Usługa zlecenia pracy** dodano pole **Zamówienie zawiera tylko zewnętrznie obsługiwane produkty** i ono jest wyświetlane na stronie. Jest ono używane do regularnego sprawdzania, czy usługa zlecenia pracy jest zarządzana w programie Finance and Operations. To ple pomaga zagwarantować, że użytkownicy nie będą synchronizowali usług zleceń pracy nieznanych rozwiązaniu Finance and Operations.
- Do jednostki **Usługa zlecenia pracy** dodano pole **Stan systemowy w nagłówku** i ono jest wyświetlane na stronie. Jest ono używane do regularnego sprawdzania systemowego stanu zlecenia pracy i pomaga zagwarantować poprawne filtrowanie, gdy usługi zlecenia pracy są synchronizowane z programem Finance and Operations. Gdy filtry zostaną ustawione w zadaniach integracji, informacja z pola **Stan systemowy w nagłówku** jest także używana do określenia, czy mają być synchronizowane wartości szacowane, czy używane.
- Pole **Czas trwania w godzinach** przechowuje wartość z pola **Czas trwania** po jej przekonwertowaniu z minut na godziny. To pole jest używane do integracji i nie jest wyświetlane w interfejsie użytkownika.
- Pole **Szacowany czas trwania w godzinach** przechowuje wartość z pola **Szacowany czas trwania** po jej przekonwertowaniu z minut na godziny. To pole jest używane do integracji i nie jest wyświetlane w interfejsie użytkownika.
- Pole **Zafakturowana kwota jednostkowa** przechowuje kwotę, która została zafakturowana za faktycznie użytą jednostkę. Wartość jest obliczana przez podzielenie wartości z pola **Łączna kwota** przez wartość w polu **Ilość rzeczywista**. To pole jest używane do integracji z systemami, które nie obsługują różnych wartości ilości użytej i ilości zafakturowanej. Pole nie jest wyświetlane w interfejsie użytkownika.
- Wartość w polu **Zafakturowana kwota rabatu** jest obliczana jako wartość **Kwota rabatu** powiększona o zaokrąglenie z obliczania wartości **Zafakturowana kwota jednostkowa**. To pole jest używane do integracji i nie jest wyświetlane w interfejsie użytkownika.
- Pole **Zewnętrzny wiersz zamówienia** zawiera obliczony ujemny numer wiersza zamówienia, którego można używać w systemach zewnętrznych, gdzie są łączone wiersze produktów i usług zleceń pracy. To pole sprawia, że wstawiane produkty zleceń pracy mogą mieć dodatnie numery wierszy, a usługi zleceń pracy ujemne numery wierszy. Wartość tego pola jest obliczana przez pomnożenie wartości pola **Wiersz zamówienia** przez -1. Pole nie jest wyświetlane w interfejsie użytkownika.
- Wartość w polach **Użyte** jest resetowana na **0** (zero), jeśli w usłudze zlecenia pracy wartość w polu **Stan wiersza** zostanie zmieniona z **Użyte** na **Oszacowany** z jakiegokolwiek powodu. Ta zmiana pomaga zapobiec sytuacjom, gdy ilość użyta wprowadzona przez pomyłkę zostanie wykorzystana w synchronizacji, jeżeli pole **Stan wiersza** ma wartość **Oszacowany**, a opcja **Stan systemowy w nagłówku** ma wartość **Zamknięte — zaksięgowane**.

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

Przed zsynchronizowaniem zleceń pracy należy zaktualizować poniższe ustawienia w systemach.

### <a name="setup-in-field-service"></a>Konfiguracja w programie Field Service

- Upewnij się, że numeracja używana do zleceń pracy w programie Field Service nie nakłada się na numerację używaną do zamówień sprzedaży w programie Finance and Operations. W przeciwnym razie istniejące zamówienia sprzedaży mogą być niepoprawnie aktualizowane w aplikacji Field Service lub Finance and Operations.
- W polu **Tworzenie faktury do zlecenia pracy** musi być ustawiona wartość **Nigdy**, ponieważ fakturowanie będzie wykonywane w programie Finance and Operations. Wybierz kolejno opcje **Field Service** \> **Ustawienia** \> **Administracja** \> **Ustawienia programu Field Service** i upewnij się, że w polu **Tworzenie faktury do zlecenia pracy** jest ustawiona wartość **Nigdy**.

### <a name="setup-in-finance-and-operations"></a>Konfiguracja w programie Finance and Operations

Aby działała integracja zleceń pracy, trzeba skonfigurować pochodzenie sprzedaży. Pochodzenie sprzedaży służy w programie Finance and Operations do odróżniania zamówień sprzedaży, które zostały utworzone na podstawie zleceń pracy w programie Field Service. Jeśli zamówienie sprzedaży ma pochodzenie sprzedaży typu **Integracja zlecenia**, w nagłówku zamówienia sprzedaży znajduje się pole **Zewnętrzny stan zlecenia**. Ponadto pochodzenie sprzedaży pomaga zagwarantować, że zamówienia sprzedaży utworzone ze zleceń pracy w programie Field Service będą odfiltrowywane podczas synchronizacji zamówień sprzedaży między aplikacjami Finance and Operations i Field Service.

1. Wybierz kolejno opcje **Sprzedaż i marketing** \> **Ustawienia** \> **Zamówienia sprzedaży** \> **Pochodzenie sprzedaży**.
2. Wybierz opcję **Nowy**, aby utworzyć nowe pochodzenie sprzedaży.
3. W polu **Pochodzenie sprzedaży** nadaj nazwę pochodzeniu sprzedaży, taką jak **ZleceniePracy**.
4. W polu **Opis** wprowadź opis, taki jak **Zlecenie pracy w programie Field Service**.
5. Zaznacz pole wyboru **Przypisanie typu pochodzenia**.
6. W polu **Typ pochodzenia sprzedaży** ustaw wartość **Integracja zlecenia**.
7. Wybierz opcję **Zapisz**.


### <a name="setup-in-data-integration"></a>Konfiguracja w narzędziu Integracja danych.

Upewnij się, istnieje wartość **Klucz integracji** dla jednostki **msdyn_workorders**
1. Przejdź do narzędzia Integracja danych.
2. Wybierz kartę **Zestaw połączeń**.
3. Wybierz zestaw połączeń używany do synchronizacji zleceń pracy.
4. Wybierz kartę **Klucz integracji**.
5. Znajdź jednostkę msdyn_workorders i sprawdź, czy został dodany klucz **msdyn_name (numer zlecenia pracy)**. Jeśli nie jest widoczny, dodaj go, klikając opcję **Dodaj klucz**, a następnie opcję **Zapisz** u góry strony.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderheader"></a>Zlecenia pracy na zamówienia sprzedaży (Field Service na Fin and Ops): WorkOrderHeader

Filtr: (msdyn_systemstatus ne 690970005) i (msdyn_systemstatus ne 690970000) i (msdynce_hasexternallymaintainedproductsonly eq true)

[![Mapowanie szablonu w integracji danych](./media/FSWorkOrder1.png )](./media/FSWorkOrder1.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderservicelineestimate"></a>Zlecenia pracy na zamówienia sprzedaży (Field Service na Fin and Ops): WorkOrderServiceLineEstimate

Filtr: (msdynce_headersystemstatus ne 690970005) i (msdynce_headersystemstatus ne 690970000) i (msdynce_orderhasexternalmaintainedproductsonly eq true) i (msdyn_linestatus eq 690970000) i (msdynce_headersystemstatus ne 690970004)

[![Mapowanie szablonu w integracji danych](./media/FSWorkOrder2.png )](./media/FSWorkOrder2.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderservicelineused"></a>Zlecenia pracy na zamówienia sprzedaży (Field Service na Fin and Ops): WorkOrderServiceLineUsed

Filtr: (msdynce_headersystemstatus ne 690970005) i (msdynce_headersystemstatus ne 690970000) i (msdynce_orderhasexternalmaintainedproductsonly eq true) i ((msdyn_linestatus eq 690970001) lub (msdynce_headersystemstatus eq 690970004))

[![Mapowanie szablonu w integracji danych](./media/FSWorkOrder3.png )](./media/FSWorkOrder3.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderproductlineestimate"></a>Zlecenia pracy na zamówienia sprzedaży (Field Service na Fin and Ops): WorkOrderProductLineEstimate

Filtr: (msdynce_headersystemstatus ne 690970005) i (msdynce_headersystemstatus ne 690970000) i (msdynce_orderhasexternalmaintainedproductsonly eq true) i (msdyn_linestatus eq 690970000) i (msdynce_headersystemstatus ne 690970004) i (msdyn_allocated eq true)

[![Mapowanie szablonu w integracji danych](./media/FSWorkOrder4.png )](./media/FSWorkOrder4.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderproductlineused"></a>Zlecenia pracy na zamówienia sprzedaży (Field Service na Fin and Ops): WorkOrderProductLineUsed

Filtr: (msdynce_headersystemstatus ne 690970005) i (msdynce_headersystemstatus ne 690970000) i (msdynce_orderhasexternalmaintainedproductsonly eq true) i ((msdyn_linestatus eq 690970001) lub (msdynce_headersystemstatus eq 690970004) lub (msdyn_allocated ne true))

[![Mapowanie szablonu w integracji danych](./media/FSWorkOrder5.png )](./media/FSWorkOrder5.png)

