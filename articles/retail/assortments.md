---
title: "Zarządzanie asortymentem"
description: "W tym temacie wyjaśniono podstawowe pojęcia dotyczące zarządzania asortymentem w programie Microsoft Dynamics 365 for Retail oraz omówiono różne opcje projektu wdrożenia."
author: jblucher
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Retail, Operations
ms.search.region: Global
ms.author: jeffbl
ms.search.validFrom: 2017-11-21
ms.dyn365.ops.version: Application update 5
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 033968667048faf475b13f8fb95e693dc26935ca
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="assortment-management"></a>Zarządzanie asortymentem
[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Przegląd
Program Microsoft Dynamics 365 for Retail zawiera funkcję *asortymentów*, która pozwala zarządzać dostępnością produktów w różnych kanałach. Asortymenty decydują, które produkty są dostępne w konkretnych sklepach i okresach.

W aplikacji Retail asortyment to mapowanie jednego lub więcej kanałów (lub grup kanałów, gdy są używane hierarchie organizacyjne) na jeden lub więcej produktów (lub grup produktów, gdy są używane hierarchie kategorii).

Całościowa kombinacja produktów w kanale zależy od opublikowanych asortymentów przypisanych do kanału. W związku z tym dla każdego kanału można skonfigurować wiele aktywnych asortymentów.

### <a name="basic-assortment-setup"></a>Podstawowa konfiguracja asortymentu
W poniższym przykładzie dla każdego sklepu jest konfigurowany unikatowy asortyment. W tym przypadku tylko produkt 1 jest dostępny w sklepie 1 oraz tylko produkt 2 jest dostępny w sklepie 2.

![Każdy produkt jest dostępny w jednym sklepie](./media/Managing-assortments-figure1.png)

Aby produkt 2 był dostępny w sklepie 1, można dodać ten produkt do asortymentu 1.

![Produkt 2 dodany do asortymentu 1](./media/Managing-assortments-figure2.png)

Alternatywnie można dodać sklep 1 do asortymentu 2.

![Sklep 1 dodany do asortymentu 2](./media/Managing-assortments-figure3.png)

### <a name="organization-hierarchies"></a>Hierarchie organizacyjne
W sytuacjach, gdzie ten sam produkt jest sprzedawany w różnych kanałach, asortymenty można skonfigurować za pomocą hierarchii organizacyjnej Asortyment sieci sprzedaży. Podczas dodawania węzłów z tej hierarchii zostaną uwzględnione wszystkie kanały istniejące w tym węźle i jego węzłach podrzędnych.

![Hierarchia organizacyjna](./media/Managing-assortments-figure4.png)

### <a name="product-categories"></a>Kategorie produktów
Podobnie po stronie produktu można dołączyć grupy produktów, używając hierarchii kategorii produktów. Można skonfigurować asortymenty, dodając jeden lub więcej węzłów hierarchii kategorii. W takim przypadku asortyment będzie obejmował wszystkie produkty z tego węzła kategorii i jego węzłów podrzędnych.

![Kategorie produktów](./media/Managing-assortments-figure5.png)

### <a name="excluded-products-or-categories"></a>Wykluczone produkty i kategorie
Poza włączaniem produktów i kategorii do asortymentów można także użyć opcji Wyklucz, aby wskazać konkretne produkty lub kategorii, które nie powinny się znaleźć w asortymentach. W poniższym przykładzie chcesz dołączyć wszystkie produkty do wybranej kategorii, z wyjątkiem produktu 2. W takim wypadku nie trzeba definiować asortymentu produkt po produkcie ani tworzyć dodatkowych węzłów kategorii. Zamiast tego można po prostu dodać kategorię, ale wykluczyć określony produkt.

> [!NOTE]
> Jeśli produkt jest z definicji zarówno dołączony, jak i wykluczony z jednego lub więcej asortymentów, zawsze będzie uznawany za wykluczony.

![Wykluczone produkty](./media/Managing-assortments-figure6.png)

### <a name="global-and-released-products"></a>Produkty globalne i zwolnione
Asortymenty są definiowane na poziomie globalnym i mogą zawierać kanały z wielu firm. Produkty i kategorie zawarte w asortymentach również są współużytkowane przez firmy. Jednak produkt musi zostać zwolniony, zanim będzie go można faktycznie sprzedać, zamówić, policzyć lub przyjąć w kanale (na przykład w aplikacji punktu sprzedaży \[POS\]). W związku z tym mimo że dwa sklepy w różnych firmach mogą mieć wspólny asortyment zawierający te same produkty, produkty będą dostępne tylko wtedy, gdy zostaną zwolnione do tych firm.

### <a name="dynamic-and-static-assortments"></a>Asortymenty dynamiczne i statyczne
Asortymenty można definiować z ustawionymi określonymi kanałami i produktami lub poprzez dołączenie jednostek organizacyjnych i kategorii. Asortymenty zawierające odwołania do tych grup są traktowane jako asortymenty dynamiczne. Jeśli definicja lub zawartość tych grup zmieni się w czasie, gdy asortyment jest aktywny, zmieni się również definicja asortymentu.

Na przykład asortyment został pierwotnie zdefiniowany i opublikowany w taki sposób, że odwołuje się do kategorii produktów. Jeśli później do tej kategorii zostaną dodane kolejne produkty, będą one automatycznie włączone do definicji istniejącego asortymentu. Nie trzeba ręcznie dodawać nowych produktów do asortymentu. Podobnie jeśli jednostka organizacyjna zostanie dodana do innego węzła, jej asortyment będzie automatycznie korygowany zgodnie z nową definicją.

### <a name="stopped-products"></a>Zatrzymane produkty 
Można „zatrzymać” zwolnione produkty dla procesu sprzedaży, włączając odpowiednie ustawienie w oknie ustawień **Ustawienia domyślne zamówień**. Ustawienie to jest najczęściej używane, gdy produkt znajduje się pod koniec swojego cyklu życia i nie powinien już być sprzedawany w żadnym kanale. Asortymenty respektują to ustawienie i zatrzymane produkty nie będą w nich umieszczane, niezależnie od konfiguracji asortymentów.

### <a name="blocked-products"></a>Zablokowane produkty
Oprócz zatrzymywania sprzedaży produktu można również tymczasowo zablokować sprzedaż. To ustawienie można skonfigurować na karcie **Sprzedaż detaliczna** dla zwolnionego produktu. Zablokowane produkty są nadal umieszczane w asortymentach, ale w aplikacji POS będzie wyświetlany komunikat z informacją, że produktu nie można sprzedawać.

### <a name="date-effectivity"></a>Obowiązywanie dat
Asortymenty mają daty obowiązywania. Dlatego sprzedawcy detaliczni mogą skonfigurować, kiedy produkty powinny i nie powinny być dostępne w poszczególnych kanałach. Można zdefiniować i opublikować asortymenty z wyprzedzeniem oraz określić im daty rozpoczęcia i zakończenia. Produkty automatycznie staną się dostępne lub niedostępne w podanych dniach.

### <a name="process-assortments-batch-job"></a>Zadanie wsadowe Przetwarzaj asortymenty
Asortymenty zdefiniowane w aplikacji Retail muszą zostać przetworzone, zanim będą mogły zacząć obowiązywać. Przetwarzanie odbywa się z następujących powodów:

- Definicje asortymentów muszą zostać zdenormalizowane, tak aby kanały mogły łatwiej z nich korzystać. Kombinacje produktów w kanale można zdefiniować za pomocą wielu asortymentów obejmujących różne zakresy dat. Gdy niektóre z tych informacji zostaną obliczone z wyprzedzeniem na serwerze, poprawi to szybkość operacji w kanale.
- Produkty i kanały w asortymencie mogą się zmieniać poza samym asortymentem. Asortymenty dynamiczne, które zawierają odwołania do kategorii lub jednostek organizacyjnych, muszą być przetwarzane co pewien czas, tak aby uwzględniały lub wykluczały rekordy w oparciu o ich bieżące przypisania.

## <a name="implementation-considerations"></a>Uwagi dotyczące implementacji
Planując i organizując asortymenty dla swojego wdrożenia aplikacji Retail, należy wziąć pod uwagę następujące wymagania implementacyjne:

- **Replikacja danych i rozmiar bazy danych** — asortymenty pomagają zaspokajać potrzebę biznesową zarządzania dostępnością produktów, ale są również ważnym narzędziem do zarządzania wielkością baz danych kanałów i offline. Dobrze zarządzane asortymenty zmniejszają ilość danych, jaka musi być przetwarzana i replikowana do baz danych kanałów i offline. Ograniczają również liczbę rekordów, jaką należy trwale utrzymywać. Mniejsza liczba rekordów w bazach danych poprawia wydajność działania podczas dodawania elementów do transakcji, wyszukiwania i przeglądania produktów.
- **Ustawianie dat obowiązywania/wygasania asortymentów** — jednym z najbardziej efektywnych narzędzi do zarządzania liczbą produktów w bazach danych kanałów i offline jest ustalanie dat obowiązywania asortymentów. Jeśli pozostawisz bezterminowość (brak wygasania) asortymentów produktów sezonowych lub zbliżających się do końca cyklu życia, bazy danych będą się rozrastać bez końca. Do zarządzania taką sytuacją można stosować różne podejścia. Na przykład można prowadzić oddzielne asortymenty na produkty sezonowe i produkty, które są zawsze dostępne.
- **Sprzedaż i zwroty poza asortymentami** — ta funkcja pozwala sprzedawcom detalicznym efektywnie zarządzać liczebnością asortymentów poprzez ograniczenie dostępności produktów tylko do tych, które należą do podstawowego asortymentu sklepu. Pomaga również reagować w sytuacjach, gdy produkt został omyłkowo pominięty z asortyment lub zwrócony poza datami obowiązywania asortymentu.

Jeśli dane produktu nie istnieją w bazie danych kanału, aplikacja POS wykonuje w czasie rzeczywistym wywołania do centrali w celu pobrania wymaganych informacji, dzięki czemu produkt można sprzedać, zwrócić lub umieścić w zamówieniu klienta. Informacje o produkcie pobrane w ten sposób są dostępne tylko w zakresie danej transakcji. Produkt nie jest dodawany do definicji asortymentu. W związku później również będą wykonywane wywołania w czasie rzeczywistym tylko w razie potrzeby.

