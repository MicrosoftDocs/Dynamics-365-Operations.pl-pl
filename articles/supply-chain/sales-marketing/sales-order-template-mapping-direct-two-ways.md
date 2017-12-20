---
title: "Synchronizacja zamówień sprzedaży bezpośrednio między rozwiązaniami Sales a Finance and Operations"
description: "Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do rozpoczynania synchronizacji zamówień sprzedaży między programami Microsoft Dynamics 365 for Sales i Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: ChristianRytt
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 7a828090fa34eb96d2b557eb06e48ad05b421ae8
ms.openlocfilehash: 9aa8c78f5aea5a818d517c2baa9051750b132fc6
ms.contentlocale: pl-pl
ms.lasthandoff: 11/20/2017

---

# <a name="synchronization-of-sales-orders-directly-between-sales-and-finance-and-operations"></a>Synchronizacja zamówień sprzedaży bezpośrednio między rozwiązaniami Sales a Finance and Operations

[!include[banner](../includes/banner.md)]

Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do rozpoczynania synchronizacji zamówień sprzedaży między programami Microsoft Dynamics 365 for Sales i Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.

## <a name="templates-and-tasks"></a>Szablony i zadania

Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi PowerApps](https://preview.admin.powerapps.com/dataintegration). Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.

Następujące szablony i podstawowe zadania są używane do rozpoczynania synchronizacji zamówień sprzedaży bezpośrednio między programami Sales oraz Finance and Operations:

- **Nazwy szablonów w integracji danych:** 

    - Zamówienia sprzedaży (z Sales do Fin and Ops) — bezpośrednie
    - Zamówienia sprzedaży (z Fin and Ops do Sales) — bezpośrednie

- **Nazwy zadań w projekcie integracji danych:**

    - OrderHeader
    - OrderLine

Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować nagłówki i wiersze faktur sprzedaży:

- Produkty (z Fin and Ops do Sales) — bezpośrednie
- Konta (Sales do Fin and Ops) — bezpośrednie (jeśli są używane)
- Kontakty z odbiorcami (z Sales do Fin and Ops) — bezpośrednie (jeśli używane)

## <a name="entity-set"></a>Zestaw jednostek

| Finance and Operations  | Sprzedaż             |
|-------------------------|-------------------|
| Nagłówki zamówień sprzedaży CDS | SalesOrders       |
| Wiersze zamówienia sprzedaży CDS   | SalesOrderDetails |

## <a name="entity-flow"></a>Przepływ jednostek

Zamówienia sprzedaży są tworzone w rozwiązaniu Sales i synchronizowane z rozwiązaniem Finance and Operations po uruchomieniu polecenia **Uruchom projekt** dla projektu na podstawie szablonu **Zamówienia sprzedaży (z Sales do Fin and Ops) — bezpośrednie**. Zamówienia sprzedaży można uaktywnić i zsynchronizować z rozwiązania Sales tylko jeżeli opcja **Zamawianie produktów** zawiera wyłącznie produkty obsługiwane zewnętrznie. Dlatego nie mogą występować produkty dopisane. Po uaktywnieniu zamówienia zamówienie sprzedaży zmienia się na tylko do odczytu w interfejsie użytkownika. W tym momencie aktualizacje są dokonywane z rozwiązania Finance and Operations. Gdy zamówienie sprzedaży uzyska stan **Potwierdzone**, można użyć projektu opartego na szablonie **Zamówienia sprzedaży (z Fin and Ops do Sales) — bezpośrednie** do synchronizowania wszystkich aktualizacji lub stanu realizacji z rozwiązania Finance and Operations do rozwiązania Sales.

Nie trzeba tworzyć zamówień w rozwiązaniu Sales. Można utworzyć nowe zamówienia sprzedaży w rozwiązaniu Finance and Operations. Gdy zamówienie uzyska status **Potwierdzone** jest synchronizowane z rozwiązaniem Sales zgodnie z opisem w poprzednim akapicie.

W rozwiązaniu Finance and Operations filtry w szablonie zapewniają, że w synchronizacji uwzględniane są tylko odpowiednie zamówienia sprzedaży.

- W zamówieniu sprzedaży klient zamawiający i fakturujący muszą pochodzić z rozwiązania Sales, aby zostali uwzględnieni w synchronizacji. W rozwiązaniu Finance and Operations pola **OrderingCustomerIsExternallyMaintained** i **InvoiceCustomerIsExternallyMaintained** służą do filtrowania zamówień sprzedaży z jednostek danych.
- Zamówienie sprzedaży w rozwiązaniu Finance and Operations musi zostać potwierdzone. Z rozwiązaniem Sales są synchronizowane tylko potwierdzone zamówienia sprzedaży lub zamówienia sprzedaży o wyższym statusie przetwarzania, takim jak **Wysłano** lub **Zafakturowano**.
- Po utworzeniu lub zmodyfikowaniu zamówienia sprzedaży należy wykonać zadanie wsadowe **Obliczanie sum sprzedaży** w rozwiązaniu Finance and Operations. Z rozwiązaniem Sales zostaną synchronizowane tylko zamówienia sprzedaży, dla których obliczono sumy sprzedaży.

## <a name="freight-tax"></a>Podatek od frachtu

Rozwiązanie Sales nie obsługuje podatku na poziomie nagłówka, ponieważ podatek jest przechowywany na poziomie wiersza. Aby obsługiwać podatek na poziomie nagłówka z rozwiązania Finance and Operations, na przykład podatek od frachtu, system synchronizuje podatek z rozwiązaniem Sales jako produkt wpisany o nazwie **Podatek od frachtu** i zawiera on kwotę podatku z rozwiązania Finance and Operations. Dzięki temu można użyć standardowego obliczenia ceny w rozwiązaniu Sales do określenia sum, nawet jeżeli istnieje podatek na poziomie nagłówka z rozwiązania Finance and Operations.

## <a name="discount-calculation-and-rounding"></a>Obliczanie i zaokrąglanie rabatów

Model obliczania rabatu w rozwiązaniu Sales różni się od modelu obliczania rabatu w rozwiązaniu Finance and Operations. W rozwiązaniu Finance and Operations kwota ostatecznego rabatu w wierszu sprzedaży może wynikać z połączenia kwot rabatu i procentów rabatu. Jeżeli ta kwota ostatecznego rabatu zostanie podzielona przez ilość w wierszu, może nastąpić zaokrąglenie. Jednakże to zaokrąglenie nie jest uznawane, jeżeli zaokrąglony rabat na jednostkę zostanie zsynchronizowany z rozwiązaniem Sales. Aby zapewnić, że pełna kwota rabatu z wiersza sprzedaży w rozwiązaniu Finance and Operations zostanie prawidłowo zsynchronizowana z rozwiązaniem Sales, należy zsynchronizować pełną kwotę bez dzielenia przez ilość w wierszu. Dlatego w rozwiązaniu Sales należy zdefiniować opcję **Metoda kalkulacji rabatów** jako **Pozycja w wierszu**.

Po zsynchronizowaniu wiersza zamówienia sprzedaży z rozwiązania Sales do rozwiązania Finance and Operations używana jest pełna kwota rabatu wiersza. Ponieważ rozwiązanie Finance and Operations nie ma pola umożliwiającego przechowywania pełnej kwoty rabatu dla wiersza, kwota jest dzielona przez ilość i przechowywana w polu **Rabat wiersza**. Każde zaokrąglenie powstałe podczas tego dzielenia jest przechowywane w polu **Opłaty od sprzedaży** w wierszu sprzedaży.

### <a name="example"></a>Przykład

**Synchronizacja z rozwiązania Sales do rozwiązania Finance and Operations**

- **Sprzedaż:** Ilość = 3, rabat na wiersz = 10,00 USD
- **Finance and Operations:** Ilość = 3, kwota rabatu w wierszu = 3,33 USD, opłata za sprzedaż = -0,01 USD 

**Synchronizacja z rozwiązania Finance and Operations do rozwiązania Sales**

- **Finance and Operations:** Ilość = 3, kwota rabatu w wierszu = 3,33 USD, opłata za sprzedaż = -0,01 USD
- **Sprzedaż:** Ilość = 3, rabat na wiersz = (3 × 3,33 USD) + 0,01 USD = 10,00 USD

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

Nowe pola zostały dodane do jednostki **Zamówienie** i są wyświetlane na stronie:

- **Jest obsługiwane zewnętrznie**— ustaw tę opcję na **Tak**, gdy zamówienie pochodzi z programu Finance and Operations.
- **Stan przetwarzania** — to pole służy do wyświetlania stanu przetwarzania zamówienia w rozwiązaniu Finance and Operations. Dostępne są następujące wartości:

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

Ustawienie **Zawiera tylko zewnętrznie obsługiwane produkty** jest używane podczas aktywacji zamówienia w celu umożliwienia ciągłego śledzenia, czy zamówienie sprzedaży zawiera wyłącznie zewnętrznie obsługiwane produkty. Jeśli zamówienie sprzedaży zawiera tylko zewnętrznie obsługiwane produkty, są one obsługiwane w programie Finance and Operations. To ustawienie pomaga zagwarantować, że nie będziesz uaktywniać i próbować zsynchronizować wierszy zamówienia sprzedaży z produktami nieznanymi rozwiązaniu Finance and Operations.

W przypadku zamówień obsługiwanych zewnętrznie przyciski **Utwórz fakturę**, **Anuluj zamówienie**, **Oblicz ponownie**, **Pobierz produkty** i **Wyszukaj adres** na stronie **Zamówienie sprzedaży** są ukryte, ponieważ faktury zostaną utworzone w rozwiązaniu Finance and Operations i zsynchronizowane z rozwiązaniem Sales. Tych zamówień nie można edytować, ponieważ informacje o zamówieniu sprzedaży zostaną zsynchronizowane z rozwiązania Finance and Operations po uaktywnieniu.

Stan zamówienia sprzedaży pozostanie **Aktywny**, aby zapewnić przepływ zmian z rozwiązania Finance and Operations do zamówienia sprzedaży w programie Sales. Aby kontrolować to zachowanie, ustaw wartość domyślną pola **Kod stanu \[Stan\]** na **Aktywne** w projekcie integracji danych.

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

Przed zsynchronizowaniem zamówień sprzedaży należy zaktualizować poniższe ustawienia w systemach.

### <a name="setup-in-sales"></a>Konfiguracja w programie Sales

- Upewnij się, że skonfigurowano uprawienia dla zespołu, do którego przypisany jest użytkownik z połączenia rozwiązania Sales. Jeżeli korzystasz z danych demonstracyjnych, zwykle użytkownik, ale nie zespół ma dostęp w trybie administratora. Jeżeli zespół nie ma dostępu w trybie administratora po uruchomieniu projektu z integracji danych, zostanie wyświetlony komunikat o błędzie z informacją o braku zespołu sprzedającego.

    Przejdź do okna **Ustawienia** &gt; **Zabezpieczenia** &gt; **Zespoły** wybierz odpowiedni zespół, wybierz opcję **Zarządzaj rolami** i wybierz rolę o odpowiednich uprawnieniach, na przykład **Administrator systemu**.

- Przejdź do okna **Ustawienia** &gt; **Administracja** &gt; **Ustawienia systemu** &gt; **Sprzedaż** i sprawdź, czy używane są następujące ustawienia:

    - Opcja **Użyj systemowego obliczania cen** jest ustawiona na **Tak**.
    - Pole **Metoda kalkulacji rabatów** jest ustawione na **Pozycja w wierszu**.

### <a name="setup-in-finance-and-operations"></a>Konfiguracja w programie Finance and Operations

- Przejdź do okna **Sprzedaż i marketing** &gt; **Zadania okresowe** &gt; **Obliczanie sum sprzedaży** i skonfiguruj zadanie tak, aby było uruchamiane jako zadanie wsadowe. Ustaw opcję **Oblicz sumy dla zamówień sprzedaży** na **Tak**. Ten krok jest ważny, ponieważ z rozwiązaniem Sales zostaną synchronizowane tylko zamówienia sprzedaży, dla których obliczono sumy sprzedaży. Częstotliwość zadania wsadowego powinna być zgodna z częstotliwością synchronizacji zamówienia sprzedaży.

### <a name="setup-in-the-sales-orders-sales-to-fin-and-ops---direct-data-integration-project"></a>Konfiguracja w projekcie integracji Zamówienia sprzedaży (z Sales do Fin and Ops) — projekt integracji danych bezpośrednich

- Sprawdź, czy istnieje wymagane mapowanie dla **Shipto\_country** na **DeliveryAddressCountryRegionISOCode**. Pustą wartość można ustawić jako domyślną w mapie wartości, aby wyeliminować konieczność wpisywania kraju dla zamówień krajowych. Ustaw lewą stronę na „Puste” a prawą na odpowiedni kraj lub region.

    Wartość szablonu to mapa wartości, w które zmapowanych jest kilka krajów lub regionów i gdzie wartość„Puste” = US.

### <a name="setup-in-the-sales-orders-fin-and-ops-to-sales---direct-data-integration-project"></a>Konfiguracja w projekcie integracji Zamówienia sprzedaży (Fin and Ops to Sales) — projekt integracji danych bezpośrednich

#### <a name="salesheader-task"></a>Zadanie SalesHeader

- Cennik jest wymagany do utworzenia zamówień w rozwiązaniu Sales. Zaktualizuj mapę wartości dla parametru **pricelevelid.name \[Nazwa cennika\]** na cennik używany w programie Sales według waluty. Dla jednej waluty można użyć cennika domyślnego. Ponadto, jeżeli masz cenniki w kilku walutach, możesz użyć mapy wartości.

    Wartość szablonu domyślnego dla parametru **pricelevelid.name \[Nazwa cennika\]** to **CRM Service USA (przykład)**.

#### <a name="salesline-task"></a>Zadanie SalesLine

- Upewnij się, że w rozwiązaniu Finance and Operations istnieje wymagana mapa wartości dla pola **SalesUnitSymbol**.
- Upewnij się, że w rozwiązaniu Sales skonfigurowano wymagane jednostki.

    Wartość szablonu zawierająca mapę wartości jest zdefiniowana dla parametru **SalesUnitSymbol** na **oumid.name**.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

> [!NOTE]
> Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.

> [!NOTE]
> Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Finance and Operations lub z rozwiązania Finance and Operations do rozwiązania Sales.

### <a name="sales-orders-fin-and-ops-to-sales---direct-orderheader"></a>Zamówienia sprzedaży (z Fin and Ops do Sales) — bezpośrednie: OrderHeader

[![Mapowanie szablonu w integracji danych](./media/sales-order-direct-template-mapping-data-integrator-1.png)](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="sales-orders-fin-and-ops-to-sales---direct-orderline"></a>Zamówienia sprzedaży (z Fin and Ops do Sales) — bezpośrednie: OrderLine

[![Mapowanie szablonu w integracji danych](./media/sales-order-direct-template-mapping-data-integrator-2.png)](./media/sales-order-direct-template-mapping-data-integrator-2.png)

### <a name="sales-orders-sales-to-fin-and-ops---direct-orderheader"></a>Zamówienia sprzedaży (z Sales do Fin and Ops) — bezpośrednie: OrderHeader

[![Mapowanie szablonu w integracji danych](./media/sales-order-direct-template-mapping-data-integrator-3.png)](./media/sales-order-direct-template-mapping-data-integrator-3.png)

### <a name="sales-orders-sales-to-fin-and-ops---direct-orderline"></a>Zamówienia sprzedaży (z Sales do Fin and Ops) — bezpośrednie: OrderLine

[![Mapowanie szablonu w integracji danych](./media/sales-order-direct-template-mapping-data-integrator-4.png)](./media/sales-order-direct-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Powiązane tematy

[Prospekt na gotówkę](prospect-to-cash.md)

