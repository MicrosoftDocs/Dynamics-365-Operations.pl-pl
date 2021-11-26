---
title: Pojęcie firmy w usługach Dataverse
description: W tym temacie opisano integrację danych firmy między Finance and Operations i Dataverse.
author: RamaKrishnamoorthy
ms.date: 08/04/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 25bd2cc0df4940f02313b3a61f69b2273e835639
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782092"
---
# <a name="company-concept-in-dataverse"></a>Pojęcie firmy w usługach Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


W Finance and Operations koncepcja *firmy* jest zarówno konstrukcją prawną, jak i konstrukcją biznesową. Jest to również granicą bezpieczeństwa i widoczności danych. Użytkownicy zawsze pracują w kontekście pojedynczej firmy, a większość danych jest rozłożona według firmy.

Dataverse nie ma równoważnej koncepcji. Najbliższa koncepcja jest *jednostką biznesową*, która jest przede wszystkim granicą bezpieczeństwa i widoczności danych użytkownika. Koncepcja ta nie ma takich samych konsekwencji prawnych lub biznesowych, co koncepcja firmy.

Ponieważ jednostka biznesowa i firma nie są równoważnymi pojęciami, nie można wymusić mapowania 1:1 między nimi co celu integracji Dataverse. Jednak ponieważ użytkownicy muszą domyślnie być w stanie widzieć te same wiersze w aplikacji i Dataverse, firma Microsoft wprowadziła nową tabelę w Dataverse o nazwie cdm\_Company. Ta tabela jest odpowiednikiem tabeli firmy w aplikacji. Aby zagwarantować, że widoczność wierszy jest równoważna między aplikacją i Dataverse od razu po zainstalowaniu, zaleca się następujące ustawienia dla danych Dataverse:

+ Dla każdego wiersza firmy w Finance and Operations, który jest włączony dla podwójnego zapisu tworzony jest skojarzony wiersz cdm\_Company.
+ Gdy wiersz cdm\_Company jest tworzony i włączony dla podwójnego zapisu, tworzona jest domyślna jednostka biznesowa o tej samej nazwie. Mimo że domyślny zespół jest tworzony automatycznie dla tej jednostki biznesowej, jednostka biznesowa nie jest używana.
+ Tworzony jest oddzielny zespół właściciela o takiej samej nazwie. Jest również związany z jednostką biznesową.
+ Domyślnie właścicielem dowolnego wiersza utworzonego i zapisywanym podwójnie w Dataverse jest zestaw do zespołu „DW Owner” połączony ze skojarzoną jednostką biznesową.

Ilustracja poniżej zawiera przykład tej konfiguracji danych w Dataverse.

![Konfiguracja danych w Dataverse.](media/dual-write-company-1.png)

Z powodu tej konfiguracji każdy wiersz związany firmą USMF będą własnością zespołu połączonego z jednostką biznesową USMF w Dataverse. W związku z tym każdy użytkownik, który ma dostęp do tej jednostki biznesowej za pośrednictwem roli zabezpieczeń, która jest ustawiona na poziomie widoczności jednostki biznesowej, może teraz widzieć te wiersze. W poniższym przykładzie pokazano, jak zespoły mogą służyć do zapewnienia prawidłowego dostępu do tych wierszy.

+ Rola „Menedżer sprzedaży” jest przypisana do członków zespołu „USMF Sales”.
+ Użytkownicy z rolą „Menedżer sprzedaży” mają dostęp do wszystkich wierszy konta należących do tej samej jednostki biznesowej, do której należą ci użytkownicy.
+ Zespół „USMF Sales” jest powiązany z jednostką biznesową USMF, o której wspomniano wcześniej.
+ W związku z tym członkowie zespołu „USMF Sales” mogą zobaczyć dowolne konto, które jest własnością użytkownika „USMF DW”, i które pochodzi z tabeli Firma USMF w Finance and Operations.

![Jak mogą być używane zespoły.](media/dual-write-company-2.png)

Jak pokazano na powyższej ilustracji, to mapowanie 1:1 między jednostką biznesową, firmą i zespołem jest tylko punktem początkowym. W tym przykładzie nowa jednostka biznesowa „Europa” jest tworzona ręcznie w Dataverse jako element nadrzędny zarówno dla DEMF, jak i ESMF. Ta nowa główna jednostka biznesowa nie ma związku z podwójnym zapisem. Jednak może służyć do zapewnienia członkom zespołu „EUR Sales” dostępu do danych konta zarówno w DEMF, jak i ESMF, ustawiając widoczność danych na **Nadrzędna/Podrzędna jednostka biznesowa** w skojarzonej roli zabezpieczeń.

Ostatnim tematem do omówienia jest to, w jaki sposób podwójny zapis określa zespół właściciela, do którego ma przypisać wiersze. To zachowanie jest kontrolowane przez kolumnę **Domyślny zespół właściciela** w wierszu cdm\_Company. Kiedy w wierszu cdm\_Company jest włączony podwójny zapis, wtyczka automatycznie tworzy skojarzoną jednostkę biznesową i zespół właściciela (jeśli jeszcze nie istnieje) i ustawia kolumnę **Domyślny zespół właściciela**. Administrator może zmienić wartość tej kolumny na inną. Jednak administrator nie może wyczyścić kolumny, dopóki w tabeli jest włączony podwójny zapis.

> [!div class="mx-imgBorder"]
![Domyślna kolumna zespołu będącego właścicielem.](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Powielanie danych i inicjowanie firmy

Integracja Dataverse powoduje wywołuje parzystość firmy za pomocą identyfikatora firmy w celu powielenia danych. Na poniższej ilustracji pokazano, że wszystkie tabele właściwe dla firmy są rozszerzane w taki sposób, że mają relacje wiele do jednego (N:1) z tabelą cdm\_Company.

> [!div class="mx-imgBorder"]
![Relacja N:1 między tabelą specyficzną dla firmy a tabelą cdm_Company.](media/dual-write-bootstrapping.png)

+ W przypadku wierszy po dodaniu i zapisaniu firmy jest ona tylko do odczytu. Dlatego użytkownicy powinni upewnić się, że została wybrana prawidłowa firma.
+ Tylko wiersze, które mają dane firmy, są uprawnione do podwójnego zapisywania między aplikacją a Dataverse.
+ W przypadku istniejących danych Dataverse inicjowanie prowadzone przez administratora będzie wkrótce dostępne.


## <a name="autopopulate-company-name-in-customer-engagement-apps"></a>Autowypełniaj nazwę firmy w aplikacjach do zakontraktowania odbiorcy

Istnieje kilka sposobów automatycznego wypełniania nazwy firmy w aplikacjach do zakontraktowania odbiorców.

+ Administrator systemu może określić domyślnie ustawioną firmę, przechodząc kolejno do sekcji **Ustawienia zaawansowane > System > Zabezpieczenia > Użytkownicy**. Otwórz formularz **Użytkownik**, a następnie w sekcji **Informacje o organizacji** określ wartość **Domyślna firma w formularzach**.

    :::image type="content" source="media/autopopulate-company-name-1.png" alt-text="Ustawienie firmy jako domyślnej w sekcji Informacje o organizacji.":::

+ Jeśli użytkownik ma dostęp do **Zapisu** w tabelą **SystemUser** na poziomie **Jednostki biznesowej**, może zmienić domyślną firmę w dowolnym formularzu, wybierając firmę z rozwijanego menu **Firma**.

    :::image type="content" source="media/autopopulate-company-name-2.png" alt-text="Zmiana nazwy firmy na nowym koncie":::

+ Jeśli masz dostęp do **Zapisu** danych w więcej niż jednej firmie, możesz zmienić domyślną firmę, wybierając wiersz należący do innej firmy.

    :::image type="content" source="media/autopopulate-company-name-3.png" alt-text="Wybór wiersza powoduje zmianę firmy domyślnej":::

+ Jeśli użytkownik jest konfiguratorem systemów lub administratorem i chce automatycznie wypełniać dane firmy w formularzu niestandardowym, może używać [zdarzeń formularzy](/powerapps/developer/model-driven-apps/clientapi/events-forms-grids). Dodaj odwołanie JavaScript do **msdyn_/DefaultCompany.js** i korzystaj z następujących zdarzeń. Można skorzystać z dowolnego formularza, na przykład formularza **Konto**.

    + Zdarzenie **OnLoad** dla formularza: należy określić kolumnę **defaultCompany**.
    + Zdarzenie **OnChange** dla kolumny **Firma**: należy określić kolumnę **updateDefaultCompany**.

## <a name="apply-filtering-based-on-the-company-context"></a>Zastosuj filtrowanie na podstawie kontekstu firmy

Aby zastosować filtrowanie na podstawie kontekstu firmy w formularzach niestandardowych lub w niestandardowych polach kolumnach wyszukiwania dodanych do standardowych formularzy, należy otworzyć formularz i użyć sekcji **Filtrowanie rekordów pokrewnych** w celu zastosowania filtru firmy. Należy to ustawić dla każdej kolumny wyszukiwania, które wymaga filtrowania na podstawie firmy w danym wierszu. Ustawienie jest wyświetlane dla **Konta** na poniższej ilustracji.

:::image type="content" source="media/apply-company-context.png" alt-text="Zastosuj kontekst firmy.":::



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]