---
title: Pojęcie firmy w usługach Common Data Service
description: W tym temacie opisano integrację danych firmy między Finance and Operations i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 444bfc1698a206ca34e67f742df63431a3b02649
ms.sourcegitcommit: 7da8811f1a7db858efb76edb0bdf857a47d07600
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/27/2020
ms.locfileid: "3728420"
---
# <a name="company-concept-in-common-data-service"></a>Pojęcie firmy w usługach Common Data Service

[!include [banner](../../includes/banner.md)]


W Finance and Operations koncepcja *firmy* jest zarówno konstrukcją prawną, jak i konstrukcją biznesową. Jest to również granicą bezpieczeństwa i widoczności danych. Użytkownicy zawsze pracują w kontekście pojedynczej firmy, a większość danych jest rozłożona według firmy.

Common Data Service nie ma równoważnej koncepcji. Najbliższa koncepcja jest *jednostką biznesową*, która jest przede wszystkim granicą bezpieczeństwa i widoczności danych użytkownika. Koncepcja ta nie ma takich samych konsekwencji prawnych lub biznesowych, co koncepcja firmy.

Ponieważ jednostka biznesowa i firma nie są równoważnymi pojęciami, nie można wymusić mapowania 1:1 między nimi co celu integracji Common Data Service. Jednak ponieważ użytkownicy muszą domyślnie być w stanie widzieć te same rekordy w aplikacji i Common Data Service, firma Microsoft wprowadziła nową jednostkę w Common Data Service o nazwie cdm\_Company. Ta jednostka jest odpowiednikiem podmiotu firmy w aplikacji. Aby zagwarantować, że widoczność rekordów jest równoważna między aplikacją i Common Data Service od razu po zainstalowaniu, zaleca się następujące ustawienia dla danych Common Data Service:

+ Dla każdego rekordu firmy w Finance and Operations, który jest włączony dla podwójnego zapisu tworzony jest skojarzony rekord cdm\_Company.
+ Gdy rekord cdm\_Company jest tworzony i włączony dla podwójnego zapisu, tworzona jest domyślna jednostka biznesowa o tej samej nazwie. Mimo że domyślny zespół jest tworzony automatycznie dla tej jednostki biznesowej, jednostka biznesowa nie jest używana.
+ Tworzony jest oddzielny zespół właściciela o takiej samej nazwie. Jest również związany z jednostką biznesową.
+ Domyślnie właścicielem dowolnego rekordu utworzonego i zapisywanym podwójnie w Common Data Service jest zestaw do zespołu „DW Owner” połączony ze skojarzoną jednostką biznesową.

Ilustracja poniżej zawiera przykład tej konfiguracji danych w Common Data Service.

![Konfiguracja danych w Common Data Service](media/dual-write-company-1.png)

Z powodu tej konfiguracji każdy rekord związany firmą USMF będą własnością zespołu połączonego z jednostką biznesową USMF w Common Data Service. W związku z tym każdy użytkownik, który ma dostęp do tej jednostki biznesowej za pośrednictwem roli zabezpieczeń, która jest ustawiona na poziomie widoczności jednostki biznesowej, może teraz widzieć te rekordy. W poniższym przykładzie pokazano, jak zespoły mogą służyć do zapewnienia prawidłowego dostępu do tych rekordów.

+ Rola „Menedżer sprzedaży” jest przypisana do członków zespołu „USMF Sales”.
+ Użytkownicy z rolą „Menedżer sprzedaży” mają dostęp do wszystkich rekordów konta należących do tej samej jednostki biznesowej, do której należą ci użytkownicy.
+ Zespół „USMF Sales” jest powiązany z jednostką biznesową USMF, o której wspomniano wcześniej.
+ W związku z tym członkowie zespołu „USMF Sales” mogą zobaczyć dowolne konto, które jest własnością użytkownika „USMF DW”, i które pochodzi z jednostki Firma USMF w Finance and Operations.

![Jak mogą być używane zespoły](media/dual-write-company-2.png)

Jak pokazano na powyższej ilustracji, to mapowanie 1:1 między jednostką biznesową, firmą i zespołem jest tylko punktem początkowym. W tym przykładzie nowa jednostka biznesowa „Europa” jest tworzona ręcznie w Common Data Service jako element nadrzędny zarówno dla DEMF, jak i ESMF. Ta nowa główna jednostka biznesowa nie ma związku z podwójnym zapisem. Jednak może służyć do zapewnienia członkom zespołu „EUR Sales” dostępu do danych konta zarówno w DEMF, jak i ESMF, ustawiając widoczność danych na **Nadrzędna/Podrzędna jednostka biznesowa** w skojarzonej roli zabezpieczeń.

Ostatnim tematem do omówienia jest to, w jaki sposób podwójny zapis określa zespół właściciela, do którego ma przypisać rekordy. To zachowanie jest kontrolowane przez pole **Domyślny zespół właściciela** w rekordzie cdm\_Company. Kiedy w rekordzie cdm\_Company jest włączony podwójny zapis, wtyczka automatycznie tworzy skojarzoną jednostkę biznesową i zespół właściciela (jeśli jeszcze nie istnieje) i ustawia pole **Domyślny zespół właściciela**. Administrator może zmienić wartość tego pola na inną. Jednak administrator nie może wyczyścić pola, dopóki w jednostce jest włączony podwójny zapis.

> [!div class="mx-imgBorder"]
![Domyślne pole zespołu będącego właścicielem](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Powielanie danych i inicjowanie firmy

Integracja Common Data Service powoduje wywołuje parzystość firmy za pomocą identyfikatora firmy w celu powielenia danych. Na poniższej ilustracji pokazano, że wszystkie jednostki właściwe dla firmy są rozszerzane w taki sposób, że mają relacje wiele do jednego (N:1) z jednostką cdm\_Company.

> [!div class="mx-imgBorder"]
![Relacja N:1 między jednostką specyficzną dla firmy a jednostką cdm_Company](media/dual-write-bootstrapping.png)

+ W przypadku rekordów po dodaniu i zapisaniu firmy jest ona tylko do odczytu. Dlatego użytkownicy powinni upewnić się, że została wybrana prawidłowa firma.
+ Tylko rekordy, które mają dane firmy, są uprawnione do podwójnego zapisywania między aplikacją a Common Data Service
+ W przypadku istniejących danych Common Data Service inicjowanie prowadzone przez administratora będzie wkrótce dostępne.


## <a name="autopopulate-company-name-in-customer-engagement-apps"></a>Autowypełniaj nazwę firmy w aplikacjach do zakontraktowania odbiorcy

Istnieje kilka sposobów automatycznego wypełniania nazwy firmy w aplikacjach do zakontraktowania odbiorców.

+ Administrator systemu może określić domyślnie ustawioną firmę, przechodząc kolejno do sekcji **Ustawienia zaawansowane > System > Zabezpieczenia > Użytkownicy**. Otwórz formularz **Użytkownik**, a następnie w sekcji **Informacje o organizacji** określ wartość **Domyślna firma w formularzach**.

    :::image type="content" source="media/autopopulate-company-name-1.png" alt-text="Ustawienie firmy jako domyślnej w sekcji Informacje o organizacji.":::

+ Jeśli użytkownik ma dostęp do **Zapisu** w encji **SystemUser** na poziomie **Jednostki biznesowej**, może zmienić domyślną firmę w dowolnym formularzu, wybierając firmę z rozwijanego menu **Firma**.

    :::image type="content" source="media/autopopulate-company-name-2.png" alt-text="Zmiana nazwy firmy na nowym koncie":::

+ Jeśli masz dostęp do **Zapisu** danych w więcej niż jednej firmie, możesz zmienić domyślną firmę, wybierając rekord należący do innej firmy.

    :::image type="content" source="media/autopopulate-company-name-3.png" alt-text="Wybór rekordu powoduje zmianę firmy domyślnej":::

+ Jeśli użytkownik jest konfiguratorem systemów lub administratorem i chce automatycznie wypełniać dane firmy w formularzu niestandardowym, może używać [zdarzeń formularzy](https://docs.microsoft.com/powerapps/developer/model-driven-apps/clientapi/events-forms-grids). Dodaj odwołanie JavaScript do **msdyn_/DefaultCompany.js** i korzystaj z następujących zdarzeń. Można skorzystać z dowolnego formularza, na przykład formularza **Konto**.

    + Zdarzenie **OnLoad** dla formularza: należy określić pole **defaultCompany**.
    + Zdarzenie **OnChange** dla pola **Firma**: należy określić pole **updateDefaultCompany**.

## <a name="apply-filtering-based-on-the-company-context"></a>Zastosuj filtrowanie na podstawie kontekstu firmy

Aby zastosować filtrowanie na podstawie kontekstu firmy w formularzach niestandardowych lub w niestandardowych polach wyszukiwania dodanych do standardowych formularzy, należy otworzyć formularz i użyć sekcji **Filtrowanie rekordów pokrewnych** w celu zastosowania filtru firmy. Należy to ustawić dla każdego pola wyszukiwania, które wymaga filtrowania na podstawie firmy w danym rekordzie. Ustawienie jest wyświetlane dla **Konta** na poniższej ilustracji.

:::image type="content" source="media/apply-company-context.png" alt-text="Zastosuj kontekst firmy":::

