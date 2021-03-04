---
title: Synchronizowanie zamówień sprzedaży w rozwiązaniu Sales bezpośrednio z elementami w rozwiązaniu Supply Chain Management
description: Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do rozpoczynania synchronizacji zamówień sprzedaży między programami Dynamics 365 Sales i Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 05/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 3eaa25f0befcff448250ba2cce8e568fa4a4c707
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435417"
---
# <a name="synchronization-of-sales-orders-directly-between-sales-and-supply-chain-management"></a>Synchronizowanie zamówień sprzedaży w rozwiązaniu Sales bezpośrednio z elementami w rozwiązaniu Supply Chain Management

[!include [banner](../includes/banner.md)]

Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do rozpoczynania synchronizacji zamówień sprzedaży między programami Dynamics 365 Sales i Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Przepływ danych w rozwiązaniu Prospekt na gotówkę

Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracji danych do synchronizacji danych między wystąpieniami Supply Chain Management a Sales. Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między usługą Supply Chain Management a Sales. Poniższa ilustracja przedstawia sposób synchronizacji danych między usługą Supply Chain Management a Sales.

[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Szablony i zadania

Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi Power Apps](https://preview.admin.powerapps.com/dataintegration). Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.

Następujące szablony i podstawowe zadania są używane do rozpoczynania synchronizacji zamówień sprzedaży bezpośrednio między programami Sales oraz Supply Chain Management:

- **Nazwy szablonów w integracji danych:** 

    - Zlecenia sprzedaży (Sales do Supply Chain Management) — bezpośrednie
    - Zlecenia sprzedaży (Supply Chain Management do Sales) — bezpośrednie

- **Nazwy zadań w projekcie integracji danych:**

    - OrderHeader
    - OrderLine

Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować nagłówki i wiersze faktur sprzedaży:

- Produkty (Supply Chain Management do Sales) — bezpośrednie
- Konta (Sales do Supply Chain Management) — bezpośrednie (jeśli używane)
- Kontakty do Odbiorcy (Sales do Supply Chain Management) — bezpośrednie (jeśli używane)

## <a name="entity-set"></a>Zestaw jednostek

| Zarządzanie łańcuchem dostaw  | Sprzedaż             |
|-------------------------|-------------------|
| Nagłówki zamówień sprzedaży CDS | SalesOrders       |
| Wiersze zamówienia sprzedaży CDS   | SalesOrderDetails |

## <a name="entity-flow"></a>Przepływ jednostek

Zamówienia sprzedaży są tworzone w rozwiązaniu Sales i synchronizowane z rozwiązaniem Supply Chain Management po uruchomieniu polecenia **Uruchom projekt** dla projektu na podstawie szablonu **Zamówienia sprzedaży (z Sales do Supply Chain Management) — bezpośrednie**. Zamówienia sprzedaży można uaktywnić i zsynchronizować z rozwiązania Sales tylko jeżeli opcja **Zamawianie produktów** zawiera wyłącznie produkty obsługiwane zewnętrznie. Dlatego nie mogą występować produkty dopisane. Po uaktywnieniu zamówienia zamówienie sprzedaży zmienia się na tylko do odczytu w interfejsie użytkownika. W tym momencie aktualizacje są dokonywane z rozwiązania Supply Chain Management. Gdy zamówienie sprzedaży uzyska stan **Potwierdzone**, można użyć projektu opartego na szablonie **Zamówienia sprzedaży (z Supply Chain Management do Sales) — bezpośrednie** do synchronizowania wszystkich aktualizacji lub stanu realizacji z rozwiązania Supply Chain Management do rozwiązania Sales.

Nie trzeba tworzyć zamówień w rozwiązaniu Sales. Można utworzyć nowe zamówienia sprzedaży w rozwiązaniu Supply Chain Management. Gdy zamówienie uzyska status **Potwierdzone** jest synchronizowane z rozwiązaniem Sales zgodnie z opisem w poprzednim akapicie.

W rozwiązaniu Supply Chain Management filtry w szablonie zapewniają, że w synchronizacji uwzględniane są tylko odpowiednie zamówienia sprzedaży.

- W zamówieniu sprzedaży klient zamawiający i fakturujący muszą pochodzić z rozwiązania Sales, aby zostali uwzględnieni w synchronizacji. W rozwiązaniu Supply Chain Management pola **OrderingCustomerIsExternallyMaintained** i **InvoiceCustomerIsExternallyMaintained** służą do filtrowania zamówień sprzedaży z jednostek danych.
- Zamówienie sprzedaży w rozwiązaniu Supply Chain Management musi zostać potwierdzone. Z rozwiązaniem Sales są synchronizowane tylko potwierdzone zamówienia sprzedaży lub zamówienia sprzedaży o wyższym statusie przetwarzania, takim jak **Wysłano** lub **Zafakturowano**.
- Po utworzeniu lub zmodyfikowaniu zamówienia sprzedaży należy wykonać zadanie wsadowe **Obliczanie sum sprzedaży** w rozwiązaniu Supply Chain Management. Z rozwiązaniem Sales zostaną synchronizowane tylko zamówienia sprzedaży, dla których obliczono sumy sprzedaży.

## <a name="freight-tax"></a>Podatek od frachtu

Rozwiązanie Sales nie obsługuje podatku na poziomie nagłówka, ponieważ podatek jest przechowywany na poziomie wiersza. Aby obsługiwać podatek na poziomie nagłówka z rozwiązania Supply Chain Management, na przykład podatek od frachtu, system synchronizuje podatek z rozwiązaniem Sales jako produkt wpisany o nazwie **Podatek od frachtu** i zawiera on kwotę podatku z rozwiązania Supply Chain Management. Dzięki temu można użyć standardowego obliczenia ceny w rozwiązaniu Sales do określenia sum, nawet jeżeli istnieje podatek na poziomie nagłówka z rozwiązania Supply Chain Management.

## <a name="discount-calculation-and-rounding"></a>Obliczanie i zaokrąglanie rabatów

Model obliczania rabatu w rozwiązaniu Sales różni się od modelu obliczania rabatu w rozwiązaniu Supply Chain Management. W rozwiązaniu Supply Chain Management kwota ostatecznego rabatu w wierszu sprzedaży może wynikać z połączenia kwot rabatu i procentów rabatu. Jeżeli ta kwota ostatecznego rabatu zostanie podzielona przez ilość w wierszu, może nastąpić zaokrąglenie. Jednakże to zaokrąglenie nie jest uznawane, jeżeli zaokrąglony rabat na jednostkę zostanie zsynchronizowany z rozwiązaniem Sales. Aby zapewnić, że pełna kwota rabatu z wiersza sprzedaży w rozwiązaniu Supply Chain Management zostanie prawidłowo zsynchronizowana z rozwiązaniem Sales, należy zsynchronizować pełną kwotę bez dzielenia przez ilość w wierszu. Dlatego w rozwiązaniu Sales należy zdefiniować opcję **Metoda kalkulacji rabatów** jako **Pozycja w wierszu**.

Po zsynchronizowaniu wiersza zamówienia sprzedaży z rozwiązania Sales do rozwiązania Supply Chain Management używana jest pełna kwota rabatu wiersza. Ponieważ rozwiązanie Supply Chain Management nie ma pola umożliwiającego przechowywania pełnej kwoty rabatu dla wiersza, kwota jest dzielona przez ilość i przechowywana w polu **Rabat wiersza**. Każde zaokrąglenie powstałe podczas tego dzielenia jest przechowywane w polu **Opłaty od sprzedaży** w wierszu sprzedaży.

### <a name="example"></a>Przykład

**Synchronizacja z Sales do Supply Chain Management**

- **Sprzedaż:** Ilość = 3, rabat na wiersz = 10,00 USD
- **Supply Chain Management** : ilość = 3, kwota rabatu wiersza = $3.33, opłata od sprzedaży =-$0,01 

**Synchronizacja z Supply Chain Management do Sales**

- **Supply Chain Management** : ilość = 3, kwota rabatu wiersza = $3.33, opłata od sprzedaży =-$0,01
- **Sprzedaż:** Ilość = 3, rabat na wiersz = (3 × 3,33 USD) + 0,01 USD = 10,00 USD

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

Nowe pola zostały dodane do jednostki **Zamówienie** i są wyświetlane na stronie:

- **Jest obsługiwane zewnętrznie**— ustaw tę opcję na **Tak**, gdy zamówienie pochodzi z programu Supply Chain Management.
- **Stan przetwarzania** — to pole służy do wyświetlania stanu przetwarzania zamówienia w rozwiązaniu Supply Chain Management. Dostępne są następujące wartości:

    - **Robocza** — stan początkowy po utworzeniu zamówienia w rozwiązaniu Sales. W rozwiązaniu Sales można edytować tylko zamówienia o tym stanie przetwarzania.
    - **Aktywna** — stan po uaktywnieniu zamówienia w rozwiązaniu Sales za pomocą przycisku **Uaktywnij**.
    - **Potwierdzone**
    - **Dokument dostawy**
    - **Zafakturowane**
    - **Pobrane**
    - **Częściowo pobrane**
    - **Częściowo zapakowano**
    - **Wysłano**
    - **Częściowo wysłane**
    - **Częściowo zafakturowane**
    - **Anulowane**

Ustawienie **Zawiera tylko zewnętrznie obsługiwane produkty** jest używane podczas aktywacji zamówienia w celu umożliwienia ciągłego śledzenia, czy zamówienie sprzedaży zawiera wyłącznie zewnętrznie obsługiwane produkty. Jeśli zamówienie sprzedaży zawiera tylko zewnętrznie obsługiwane produkty, są one obsługiwane w programie Supply Chain Management. To ustawienie pomaga zagwarantować, że nie będziesz uaktywniać i próbować zsynchronizować wierszy zamówienia sprzedaży z produktami nieznanymi rozwiązaniu Supply Chain Management.

W przypadku zamówień obsługiwanych zewnętrznie przyciski **Utwórz fakturę**, **Anuluj zamówienie**, **Oblicz ponownie**, **Pobierz produkty** i **Wyszukaj adres** na stronie **Zamówienie sprzedaży** są ukryte, ponieważ faktury zostaną utworzone w rozwiązaniu Supply Chain Management i zsynchronizowane z rozwiązaniem Sales. Tych zamówień nie można edytować, ponieważ informacje o zamówieniu sprzedaży zostaną zsynchronizowane z rozwiązania Supply Chain Management po uaktywnieniu.

Stan zamówienia sprzedaży pozostanie **Aktywny**, aby zapewnić przepływ zmian z rozwiązania Supply Chain Management do zamówienia sprzedaży w programie Sales. Aby kontrolować to zachowanie, ustaw wartość domyślną pola **Kod stanu \[Stan\]** na **Aktywne** w projekcie integracji danych.

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

Przed zsynchronizowaniem zamówień sprzedaży należy zaktualizować poniższe ustawienia w systemach.

### <a name="setup-in-sales"></a>Konfiguracja w programie Sales

- Upewnij się, że skonfigurowano uprawienia dla zespołu, do którego przypisany jest użytkownik z połączenia rozwiązania Sales. Jeżeli korzystasz z danych demonstracyjnych, zwykle użytkownik, ale nie zespół ma dostęp w trybie administratora. Jeżeli zespół nie ma dostępu w trybie administratora po uruchomieniu projektu z integracji danych, zostanie wyświetlony komunikat o błędzie z informacją o braku zespołu sprzedającego.

    Przejdź do okna **Ustawienia** &gt; **Zabezpieczenia** &gt; **Zespoły** wybierz odpowiedni zespół, wybierz opcję **Zarządzaj rolami** i wybierz rolę o odpowiednich uprawnieniach, na przykład **Administrator systemu**.

- Aby zapewnić poprawne obliczanie rabatów w aplikacjach Sales i Supply Chain Management, w ustawieniu **Metoda kalkulacji rabatów** należy zaznaczyć wartość **Pozycja w wierszu**.
- Przejdź do okna **Ustawienia** &gt; **Administracja** &gt; **Ustawienia systemu** &gt; **Sprzedaż** i sprawdź, czy używane są następujące ustawienia:

    - Opcja **Użyj systemowego obliczania cen** jest ustawiona na **Tak**.
    - Pole **Metoda kalkulacji rabatów** jest ustawione na **Pozycja w wierszu**.

### <a name="setup-in-supply-chain-management"></a>Ustawienia Supply Chain Management

- Przejdź do okna **Sprzedaż i marketing** &gt; **Zadania okresowe** &gt; **Obliczanie sum sprzedaży** i skonfiguruj zadanie tak, aby było uruchamiane jako zadanie wsadowe. Ustaw opcję **Oblicz sumy dla zamówień sprzedaży** na **Tak**. Ten krok jest ważny, ponieważ z rozwiązaniem Sales zostaną synchronizowane tylko zamówienia sprzedaży, dla których obliczono sumy sprzedaży. Częstotliwość zadania wsadowego powinna być zgodna z częstotliwością synchronizacji zamówienia sprzedaży.

Jeśli używasz również integracji zlecenia, należy skonfigurować pochodzenie sprzedaży. Pochodzenie sprzedaży służy w programie Supply Chain Management do odróżniania zamówień sprzedaży, które zostały utworzone na podstawie zleceń pracy w programie Field Service. Jeśli zamówienie sprzedaży ma pochodzenie sprzedaży typu **Integracja zlecenia**, w nagłówku zamówienia sprzedaży znajduje się pole **Zewnętrzny stan zlecenia**. Ponadto pochodzenie sprzedaży gwarantuje, że zamówienia sprzedaży utworzone ze zleceń pracy w programie Field Service będą odfiltrowywane podczas synchronizacji zamówień sprzedaży między aplikacjami Supply Chain Management i Field Service.

1. Wybierz kolejno opcje **Sprzedaż i marketing** \> **Ustawienia** \> **Zamówienia sprzedaży** \> **Pochodzenie sprzedaży**.
2. Wybierz opcję **Nowy**, aby utworzyć nowe pochodzenie sprzedaży.
3. W polu **Pochodzenie sprzedaży** nadaj nazwę pochodzeniu sprzedaży, taką jak **SalesOrder**.
4. W polu **Opis** wprowadź opis, taki jak **Zamówienie sprzedaży ze Sprzedaży**.
5. Zaznacz pole wyboru **Przypisanie typu pochodzenia**.
6. W polu **Typ pochodzenia sprzedaży** ustaw wartość **Integracja zamówienia sprzedaży**.
7. Wybierz opcję **Zapisz**.

### <a name="setup-in-the-sales-orders-sales-to-supply-chain-management---direct-data-integration-project"></a>Konfiguracja w projekcie integracji Zamówienia sprzedaży (z Sales do Supply Chain Management) — projekt integracji danych bezpośrednich

- Sprawdź, czy istnieje wymagane mapowanie dla **Shipto\_country** na **DeliveryAddressCountryRegionISOCode**. Pustą wartość można ustawić jako domyślną w mapie wartości, aby wyeliminować konieczność wpisywania kraju dla zamówień krajowych. Ustaw lewą stronę na „Puste” a prawą na odpowiedni kraj lub region.

    Wartość szablonu to mapa wartości, w które zmapowanych jest kilka krajów lub regionów i gdzie wartość„Puste” = US.

### <a name="setup-in-the-sales-orders-supply-chain-management-to-sales---direct-data-integration-project"></a>Konfiguracja w projekcie integracji Zamówienia sprzedaży (z Supply Chain Management do Sales) — projekt integracji danych bezpośrednich

#### <a name="salesheader-task"></a>Zadanie SalesHeader

- Cennik jest wymagany do utworzenia zamówień w rozwiązaniu Sales. Zaktualizuj mapę wartości dla parametru **pricelevelid.name \[Nazwa cennika\]** na cennik używany w programie Sales według waluty. Dla jednej waluty można użyć cennika domyślnego. Ponadto, jeżeli masz cenniki w kilku walutach, możesz użyć mapy wartości.

    Wartość szablonu domyślnego dla parametru **pricelevelid.name \[Nazwa cennika\]** to **CRM Service USA (przykład)**.

#### <a name="salesline-task"></a>Zadanie SalesLine

- Upewnij się, że w rozwiązaniu Supply Chain Management istnieje wymagana mapa wartości dla pola **SalesUnitSymbol**.
- Upewnij się, że w rozwiązaniu Sales skonfigurowano wymagane jednostki.

    Wartość szablonu zawierająca mapę wartości jest zdefiniowana dla parametru **SalesUnitSymbol** na **oumid.name**.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

> [!NOTE]
> Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.

> [!NOTE]
> Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Supply Chain Management lub z rozwiązania Supply Chain Management do rozwiązania Sales.

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderheader"></a>Zlecenia sprzedaży (Supply Chain Management do Sales) — bezpośrednie: OrderHeader

[![Mapowanie szablonu w integracji danych](./media/sales-order-direct-template-mapping-data-integrator-1.png)](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderline"></a>Zlecenia sprzedaży (Supply Chain Management do Sales) — bezpośrednie: OrderLine

[![Mapowanie szablonu w integracji danych](./media/sales-order-direct-template-mapping-data-integrator-2.png)](./media/sales-order-direct-template-mapping-data-integrator-2.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderheader"></a>Zlecenia sprzedaży (Sales do Supply Chain Management) — bezpośrednie: OrderHeader

[![Mapowanie szablonu w integracji danych](./media/sales-order-direct-template-mapping-data-integrator-3.png)](./media/sales-order-direct-template-mapping-data-integrator-3.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderline"></a>Zlecenia sprzedaży (Sales do Supply Chain Management) — bezpośrednie: OrderLine

[![Mapowanie szablonu w integracji danych](./media/sales-order-direct-template-mapping-data-integrator-4.png)](./media/sales-order-direct-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Powiązane tematy

[Prospekt na gotówkę](prospect-to-cash.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]