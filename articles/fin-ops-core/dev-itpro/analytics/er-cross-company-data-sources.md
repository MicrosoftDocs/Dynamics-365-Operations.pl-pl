---
title: Międzyfirmowe źródła danych w module Raportowanie elektroniczne (ER)
description: W tym temacie wyjaśniono, jak można używać źródeł danych wielu firm w Raportowaniu elektronicznym (RE).
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: dc98f060bbb27958436cd2183bb469f821d04320
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181503"
---
# <a name="cross-company-data-sources-in-electronic-reporting-er"></a>Międzyfirmowe źródła danych w module Raportowanie elektroniczne (ER)

[!include[banner](../includes/banner.md)]

Można zaprojektować formaty raportów elektronicznych ER w taki sposób, aby generowały wychodzące dokumenty w różnych formatach. Podczas generowania dokumentu format ER wywołuje źródła danych, które zostały skonfigurowane w odpowiadającym im mapowaniu modelu ER. Aby skonfigurować dostęp do tabel zgłoszeń w celu pobierania zapisów, można skorzystać z Awaryjnych źródeł danych typu **Zapisy tabeli**. Podczas uzyskiwania dostępu do tabeli, która jest współużytkowana (czyli miejsca przechowywania danych bez identyfikatora firmy), to źródło danych zwraca wszystkie rekordy. Podczas uzyskiwania dostępu do tabeli, która jest zależna od firmy (czyli miejsce przechowywania danych dla każdej firmy), to źródło danych zwraca tylko te rekordy, które zostały zapisane dla bieżącej firmy (czyli kontekst firmy pod którym pracuje format ER).

Każde źródło danych typu **Rekordy tabeli** w mapowaniu modelu może zostać teraz oznaczone jako międzyfirmowe źródło danych. Dlatego można użyć źródeł danych typu **Rekordy w tabeli**, aby uzyskać dostęp do danych przedsiębiorstwa w tabelach aplikacji.

Jeśli oznaczysz źródło danych jako międzyfirmowe, wystąpi następujące zachowanie:

- W przypadku źródła danych, które odwołuje się do którejkolwiek współużytkowanej tabeli z wyjątkiem CompanyInfo, są zwracane wszystkie rekordy istniejące w przywoływanej tabeli. 
- W przypadku źródła danych, które odwołuje się do tabeli CompanyInfo, nawet jeśli CompanyInfo jest tabelą współużytkowaną, są zwracane rekordy zawierające identyfikator firmy z określonego zakresu.
- Dla każdej tabeli zależnej od firmy źródło danych zwraca rekordy przywoływanej tabeli zawierające identyfikator firmy z podanego zakresu.

W oknie dialogowym zapytania systemowego po włączeniu opcji **Monituj o zapytanie** dla któregokolwiek źródła danych oznaczonego jako międzyfirmowe można na karcie **Zakres firm** ręcznie wybrać jedną lub więcej firm do uwzględnienia.

> [!IMPORTANT]
> Podobnie jak inne filtry, filtr firm jest utrwalany jako ostatnio używana wartość w zapytaniach po uruchomieniu formatu raportowania elektronicznego. Filtr nie jest automatycznie zmieniony, jeśli zmienisz wartość międzyfirmową dla źródła danych. Aby użyć innej wartości międzyfirmowej innego źródła danych, usuń odpowiednie zaznaczenie typowe dla użytkownika.

Dla każdego źródła danych oznaczonego jako międzyfirmowe można wybrać żądane rekordy, używając funkcji **FILTER** i **WHERE** w wyrażeniach ER. Pole **dataAreaID** może być również używane jako identyfikator firmy. Obecnie pole **dataAreaID** może zawierać wyłącznie następujące typy warunków, gdy jest używana funkcja **FILTR**:

- Obsługiwane są tylko warunki z jednym porównaniem pola **dataAreaID**.
- Dozwolone są tylko porównania zawierające wyrażenia, które nie zależą od elementów listy rekordów.

Dlatego poniższe wyrażenie jest prawidłowe.

```
FILTER (MyTable, MyTable.dataAreaID = $StringUserInputParameter)
While shown below expressions will not pass the validation:
FILTER (MyTable, MyTable.dataAreaID = MyTable2RecordsList.MyField)
FILTER (MyTable, 
    OR(
        MyTable.dataAreaID = $StringUserInputParameter1,
        MyTable.dataAreaID = $StringUserInputParameter2
    )
)
```

Domyślnie zakres obejmuje wszystkie firmy w bieżącej aplikacji. Można to jednak ograniczyć. Aby ograniczyć zakres dostęp do danych wielu firm dla jednego formatu ER, należy przypisać określonej hierarchię organizacji do tego formatu. W przypadku zdefiniowania hierarchii dla formatu ER, tylko zapisy dla podmiotów prawnych, które są prezentowane w przypisanej hierarchii są zwracane, nawet jeśli format wymaga źródła danych wielu firm. Jeśli dla formatu ER jest zdefiniowane odwołanie do hierarchii, która już nie istnieje, stosowany jest domyślny zakres, a format wywołuje źródła danych wielu firm. W tej sytuacji są zwracane rekordy wszystkich firm zdefiniowanych w aplikacji.

Należy zwrócić uwagę, że gdy opcja **Użyj wersji roboczej** jest włączona dla hierarchii organizacyjnej przypisanej do jednego formatu ER, firmy z wersji roboczej tej hierarchii będą używane do identyfikowania zakresu międzyfirmowych źródeł danych. Jeśli wersja robocza nie istnieje, zostaną użyte firmy z ostatnio opublikowanej wersji tej hierarchii organizacyjnej.

Należy zwrócić uwagę, że gdy opcja **Użyj wersji roboczej** jest wyłączona dla hierarchii organizacyjnej przypisanej do jednego formatu ER, firmy z ostatnio opublikowanej wersji tej hierarchii organizacyjnej będą używane do identyfikowania zakresu międzyfirmowych źródeł danych. Funkcja dat obowiązywania hierarchii organizacyjnych nie jest jeszcze obsługiwane w strukturze raportowania elektronicznego.

Hierarchię można przypisać do formatu na określonej stronie, na której można uzyskać dostęp z poziomu obszaru roboczego ER lub za pomocą elementu menu **Administrowanie organizacją \> Raportowanie elektroniczne \> Filtr firmy dla formatów**. Aby uzyskać dostęp do strony, użytkownik musi mieć przyznane uprawnienie **Obsługa filtrów firmy dla formatu** (ERMaintainFormatMappingLegalEntityFilters). Ograniczenie zakresu wszystkich firm dla formatu opartych na hierarchii jest stosowane oprócz ograniczenia, które użytkownik może ręcznie określić w oknie dialogowym zapytania systemowego. Przecięcie tych ograniczeń jest używane po uruchomieniu formatu.

Aby dowiedzieć się więcej o tej funkcji, należy odtworzyć przewodnik po zadaniach **Dostęp do danych ER tabel zależnych od firmy w trybie międzyfirmowym**, wchodzący w skład procesu biznesowego 7.5.4.3 Pobierania/opracowywanie składników usług/rozwiązań informatycznych (10677) i można go pobrać z [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684). Ten przewodnik zadania poprowadzi użytkownika przez proces konfigurowania mapowania modelu encja-relacja i formatu ER, aby uzyskać dostęp do tabel aplikacji w trybie międzyfirmowym.

Aby ukończyć przewodnik po zadaniach, należy pobrać następujące pliki:

- [Konfiguracja modelu ER — CrossCompanyDataAccessModel.xml](https://go.microsoft.com/fwlink/?linkid=874111)
- [Konfiguracja formatu ER — CrossCompanyDataAccessFormat.xml](https://go.microsoft.com/fwlink/?linkid=874111)
