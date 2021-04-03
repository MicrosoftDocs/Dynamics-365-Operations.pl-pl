---
title: Reguły dotyczące firm inżynieryjnych i własności danych
description: W tym temacie wyjaśniono, w jaki sposób można wykorzystać jedną lub więcej firm inżynierskich, aby zapewnić, że dane główne dla produktów są tworzone centralnie i obsługiwane. Firma inżynieryjna reprezentuje firmę, która jest właścicielem produktów technologicznych i posiada odpowiednie dane techniczne.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgEngineeringOrganization
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 837960a628ef03df4d73909e96713e256d0f5e60
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262316"
---
# <a name="engineering-companies-and-data-ownership-rules"></a>Reguły dotyczące firm inżynieryjnych i własności danych

[!include [banner](../includes/banner.md)]

## <a name="engineering-companies-and-operational-companies"></a>Firmy inżynieryjne i firmy operacyjne

Aby zapewnić, że dane główne dla produktów są tworzone centralnie i obsługiwane, można wykorzystać jedną lub więcej *firm inżynierskich*. Firma inżynieryjna reprezentuje firmę, która jest właścicielem produktów technologicznych i posiada odpowiednie dane techniczne. Jest zawsze połączona z istniejącą *osobą prawną*, która również jest firmą. Za pośrednictwem tego połączenia system ustanawia centralny punkt wejścia dla wszystkich danych technicznych związanych z produktami w firmie inżynierskiej. W tym głównym punkcie wejścia są tworzone produkty inżynieryjne i są zachowywane odpowiednie dane dotyczące inżynierii. Z niego produkty techniczne i odpowiednie dane techniczne zostaną przekazane do *firm operacyjnych*, które są podmiotami prawnymi. (Aby uzyskać więcej informacji o zarządzaniu wersjami, należy zapoznać się z tematem [Zwalnianie struktur produktów ](release-product-structure.md).) Te firmy operacyjne będą korzystały z danych technologicznych, które zostały zaprojektowane przez firmę inżynierską. Wszelkie dane logistyczne są obsługiwane lokalnie przez poszczególne firmy inżynierskie i firmy operacyjne.

Aby utworzyć firmę inżynierską, należy przejść do **ustawień zarządzania zmianami \>\>organizacji**. Wybierz opcję **Nowy**, wprowadź nazwę firmy inżynierskiej i wybierz istniejącą firmę (osobę prawną), na podstawie której ona funkcjonuje.

Jeśli system jest integrowany z zewnętrznymi systemami zarządzania cyklami życia produktów (PLM), należy utworzyć jednostkę biznesową (typ firmy), która stanie się firmą zewnętrzną.

## <a name="engineering-product-categories-and-engineering-companies"></a>Firmy inżynieryjne i kategorie produktów inżynieryjnych

*Kategorie produktów technicznych* zapewniają, że produkty techniczne są tworzone zgodnie z regułami biznesowymi firmy i działają zgodnie z potrzebami. Aby uzyskać więcej informacji na temat kategorii produktów inżynieryjnych, zapoznaj się z tematem [Wersje inżynieryjne i kategorie produktów inżynieryjnych](engineering-versions-product-category.md).

Każda kategoria produktów technicznych należy do określonej firmy inżynierskiej i może tworzyć tylko produkty należące do tej firmy. Podobnie, prawo do utrzymania produktu inżynierskiego należy również do firmy, która jest skojarzona z kategorią produktów technologicznych tego produktu.

## <a name="data-that-is-owned-by-the-engineering-company"></a>Dane będące własnością firmy inżynierskiej

Ponieważ firma inżynieryjna posiada dane techniczne, system ten kontroluje następujące procesy:

- **Tworzenie produktów inżynieryjnych:** każda firma inżynierskia może tworzyć tylko nowe produkty technologiczne oparte na kategorii produktów technologicznych, której jest właścicielem. W niektórych przypadkach firmy operacyjne utrzymują własne dane lokalne związane z tymi produktami.
- **Tworzenie wersji inżynieryjnych:** gdy firma tworzy nowy produkt inżynieryjny, system automatycznie tworzy dla niego wstępną wersję inżynierii. Tylko firma Inżynieria, która jest właścicielem, będzie mogła tworzyć nowe wersje tego produktu.
- **Tworzenie i zarządzanie atrybutami wersji inżynieryjnych:** gdy firma tworzy nowy produkt inżynieryjny, system automatycznie dodaje dla niego atrybuty inżynieryjne. Tylko firma, która jest właścicielem, będzie mogła tworzyć wartości tych atrybutów i zarządzać nimi. Aby uzyskać więcej informacji o atrybutach inżynierii, zapoznaj się z [atrybutami inżynierii i wyszukiwaniem atrybutów inżynierskich](engineering-attributes-and-search.md).
- **Tworzenie i obsługa list składowych (BOM), które są połączone z wersjami konstrukcyjnymi:** firma inżyniera będąca właścicielem może bezpośrednio połączyć BOM z wersją produktu inżynierskiego. Gdy te BOM są wydawane innym firmom, zmiany w danych technicznych BOM są ograniczone następującymi metodami:

    - Firma operacyjna nie może usunąć zwolnionych wierszy BOM.
    - Pola inżynierskie w wierszach BOM są tylko do odczytu dla firmy operacyjnej. Wszystkie pozostałe pola są polami implementacji logistycznej i mogą być edytowane przez firmę operacyjną.
    - Firma operacyjna może dodawać wiersze BOM do tego samego BOM. W ten sposób można dodawać Dodatki lokalne, takie jak materiały opakowań lub płyny smarowe.
    - Firma operacyjna może dodać zupełnie nowy lokalny BOM. Ta zmiana może być wymagana w przypadku, gdy na przykład podczas zwalniania nie jest dostarczany żaden BOM. Firma operacyjna posiada i obsługuje te lokalne BOM. Aby uzyskać więcej informacji dotyczących zarządzania wersjami, przejrzyj [struktury produktów wydania](release-product-structure.md).
    - Wszystkie lokalne BOM i wiersze BOM są zachowywane podczas aktualizacji BOM w firmie inżynierskiej.

- **Tworzenie i obsługa list składowych (BOM), które są połączone z wersjami konstrukcyjnymi:** Firma inżynieryjna będąca właścicielem może bezpośrednio połączyć BOM z wersją produktu inżynierskiego. Gdy te trasy są wydawane innym firmom, zmiany w danych technicznych tras są ograniczone następującymi metodami:

    - Inne firmy nie mogą usuwać danych technologicznych z tras.
    - Inne firmy mogą dodawać operacje do trasy. W ten sposób można dodawać lokalne etapy trasy.
    - Firmy operacyjne mogą dodać zupełnie nowy lokalny BOM. Ta zmiana może być wymagana w przypadku, gdy na przykład podczas zwalniania nie załączono żadnych tras. Firmy operacyjne posiadają i obsługują te lokalne trasy. Aby uzyskać więcej informacji dotyczących zarządzania wersjami, przejrzyj [struktury produktów wydania](release-product-structure.md).
    - Wszystkie zmiany wprowadzane lokalnie są zachowywane po ponownym zwolnieniu aktualizacji z firmy inżynierskiej do tras.

- **Tworzenie i obsługa dokumentów technicznych:** firma inżynieryjna może dołączać dokumenty technologiczne do każdej wersji inżynieryjnej.

    - Gdy te dokumenty są wydawane do innych firm, dokumenty są chronione przed usunięciem przez firmę operacyjną.
    - Inne firmy mogą dodawać zupełnie nowe dokumenty lokalne. Firma operacyjna posiada i obsługuje te lokalne dokumenty.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]