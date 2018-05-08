---
title: "Omówienie informacji o produktach"
description: "Ten temat zawiera informacje dotyczące zarządzania informacjami o produktach. Moduł Zarządzanie informacjami o produktach współpracuje ze wspólnymi definicjami produktów, kategoriami i identyfikatorami we wszystkich firmach, a także z konkretnymi konfiguracjami produktu, tak aby spełnić wszystkie wymagania procesów biznesowych."
author: cvocph
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductListPage, EcoResProductVariantMaintainWorkspace
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 72dbc5d383352d4d6444d07495fdef00137b1c7f
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

# <a name="product-information-overview"></a>Omówienie informacji o produktach

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Ten temat zawiera informacje dotyczące zarządzania informacjami o produktach. Moduł Zarządzanie informacjami o produktach współpracuje ze wspólnymi definicjami produktów, kategoriami i identyfikatorami we wszystkich firmach, a także z konkretnymi konfiguracjami produktu, tak aby spełnić wszystkie wymagania procesów biznesowych. 

Informacje o produktach stanowią podstawę wszystkich aplikacji zarządzania łańcuchami dostaw i sprzedaży detalicznej we wszystkich branżach. Odnoszą się do procesów i technologii koncentrujących się na centralnym zarządzaniu informacjami o produktach (na przykład w całych łańcuchach dostaw). Bardzo istotne jest, aby używać wspólnych definicji produktów, dokumentacji, atrybutów i identyfikatorów. W różnych modułach rozwiązania biznesowego informacje i konfiguracje specyficzne dla produktów są konieczne do zarządzania procesami biznesowymi związanymi z konkretnymi produktami, rodzinami produktów lub kategoriami produktów.

## <a name="product-definition"></a>Definicja produktu

Produkt jest definiowany głównie przez numer produktu, nazwę i opis. Są jednak potrzebne również inne dane, aby odpowiednio opisać produkt lub usługę:

- Typ produktu: towar lub usługa
- Podtyp produktu: odrębne produkty lub produkty główne
- Definicja modelu wariantu produktu:

     - Wymiary i grupy wymiarów produktu
     - Nazewnictwo produktów
     - Modele konfiguracji produktu

- Skojarzenie produktu z jedną lub więcej kategoriami
- Definicja atrybutów produktów i kategorii
- Obrazy produktu
- Załączniki
- Jednostki miary i pokrewne konwersje
- Tłumaczenia wszystkich nazw i opisów

## <a name="distribution-export-and-import-of-product-data"></a>Rozpowszechnianie, eksportowanie i importowanie danych produktów

Definicję produktu można utworzyć w programie Microsoft Dynamics 365 for Finance and Operations. Można ją także importować z systemów zarządzanie cyklem życia produktów (PLM), zarządzania danymi produktów (PDM) lub zarządzania informacjami o produktach (PIM). Jeśli jest używane więcej niż jedno wystąpienie programu Finance and Operations, jedno wystąpienie zwykle służy jako wzorzec danych produktów dla wszystkich pozostałych wystąpień. To podejście jest wspierane przez duży zbiór jednostek danych, które umożliwiają eksportowanie i importowanie danych definicji produktów z jednego wystąpienia do drugiego.

Aby umożliwić rozprowadzanie danych produktów do wielu wystąpień, program Finance and Operations umożliwia korzystanie z usługi danych wspólnych Common Data Service. Definicje produktów można wyeksportować z wystąpienia programu Finance and Operations do usługi Common Data Service. Definicje produktów mogą następnie służyć do dostarczania danych produktów innym aplikacjom biznesowym, takim jak Microsoft Dynamics 365 for Sales.

Należy zauważyć, że w dynamicznych i sprawnych organizacjach informacje o produktach zmieniają się każdego dnia. W związku z tym utrzymanie precyzyjnych i prawdziwych danych produktów jest newralgicznym samodzielnym procesem biznesowym.

## <a name="product-masters-and-product-variants"></a>Produkty główne i warianty produktów

W dynamicznym świecie, w którym produkty muszą być szybko dostosowywane do wymagań klientów, definicje produktów określają zbiory produktów, a nie odrębne produkty. W programie Microsoft Dynamics 365 for Finance and Operations te standardowe produkty są nazywane *produktami głównymi*. Produkty główne zawierają definicje i reguły określające, jak odrębne produkty są opisywane i zachowują się w procesach biznesowych. Na podstawie tych definicji można generować odrębne produkty. Te odrębne produkty są znane jako *warianty produktu*.

W programie Finance and Operations produkt główny jest skojarzony z grupą wymiarów produktu i technologią konfiguracji, aby określić reguły biznesowe. Wymiary produktu (Kolor, Rozmiar, Styl i Konfiguracja) to określony zbiór atrybutów, które mogą być używane w całej aplikacji do definiowania i śledzenia konkretnych zachowań pokrewnych produktów. Te wymiary pomagają również użytkownikom wyszukiwać i identyfikować produkty.

## <a name="configuration-technologies"></a>Technologie konfiguracji

Do wyboru są trzy technologie konfiguracji:

- Wstępnie zdefiniowane warianty są definiowane przez wstępnie zdefiniowane wymiary produktu. Definicja wariantu zawiera definicję określonej prawidłowej kombinacji wymiarów, takich jak Kolor, Styl i Rozmiar. Każda kombinacja daje w wyniku odrębny wariant produktu.
- Konfiguracja oparta na wymiarach jest zazwyczaj używana w scenariuszach produkcji i pozwala używać wymiaru Konfiguracja w definicji list składowych (BOM). Po zaznaczeniu określonej konfiguracji system używa podzbioru wierszy BOM odpowiednich dla tej konfiguracji do planowania i produkcji. Ta koncepcja jest również nazywana *globalnym BOM*, ponieważ jeden wspólny BOM jest używany do wszystkich konfiguracji produktu.
- Konfiguracja oparta na ograniczeniach używa modelu konfiguracji produktu do opisania wszystkich możliwych atrybutów i składników, które są wymagane w celu opisania wszystkich możliwych wariantów produktu w jednym modelu. Ograniczenia kombinacji atrybutów mogą być opisane za pomocą wyrażeń regularnych lub ograniczeń opartych na tabelach. Modele konfiguracji i konfiguratory mają większe znaczenie w zarządzaniu informacjami o produktach i są używane we wszystkich branżach.

Planując implementację oprogramowania Finance and Operations, bardzo ważne jest wybranie technologii konfiguracji odpowiedniej dla procesu biznesowego. Po implementacji nie można przekonwertować produktu z jednego modelu na inny.

## <a name="product-variant-model-definition-workspace"></a>Obszar roboczy Definicja modelu wariantu produktu

Obszar roboczy **Definicja modelu wariantu produktu** pokazuje całościowy obraz produktów głównych. Przedstawia także stan zwalniania produktów głównych i pokrewnych wariantów do określonych firm.

## <a name="released-products"></a>Zwolnione produkty

Produkty zwalniane do określonej firmy są nazywane *zwolnionymi produktami*. Produkty można zwalniać zbiorczo do jednej firmy lub wielu firm równocześnie. Ponieważ zależnie od konkretnej firmy może być konieczne dodanie różnych właściwości i atrybutów produktów, obszar roboczy **Obsługa zwolnionego produktu** umożliwia monitorowanie i finalizowanie ostatnio zwolnionych produktów w każdej firmie lub w podrzędnej organizacji firmy.

### <a name="released-product-maintenance-workspace"></a>Obszar roboczy Obsługa zwolnionego produktu

Obszar roboczy **Obsługa zwolnionego produktu** można konfigurować z elementu menu **Konfiguruj mój obszar roboczy**. Wybierz hierarchię kategorii i kategorię, według których chcesz wyfiltrować obszar roboczy. Aby skorygować dane odnośnego produktu w obszarze roboczym, można również zdefiniować (w dniach) horyzonty czasowe dla produktów **Ostatnio zwolnione produkty** i **Zatrzymane zwolnione produkty**.

Obszar roboczy zawiera podsumowanie kafelków i dwie listy. Lista **Otwarte sprawy** pokazuje sprawy zmian w produktach dla produktów w wybranej hierarchii kategorii produktów, który nie są jeszcze ukończone i zamknięte. Lista **Ostatnio zwolnione** zawiera produkty, które zostały zwolnione w granicach horyzontu czasowego ustawionego w konfiguracji obszaru roboczego. Dla każdego elementu na liście jest wykonywane sprawdzanie poprawności oraz wyświetlany stan tego sprawdzania. Ten stan może wskazywać, że konfiguracje wymagane dla firmy nie zostały ukończone. Korzystając z listy, można bezpośrednio uzyskać dostęp do stron **Szczegóły zwolnionego produktu**, **Obsługa atrybutów produktu**, **Obsługa kategorii produktu**, **Ustawienia domyślne zamówień** i **Tłumaczenia tekstu** w celu dokończenia żądanej konfiguracji produktu.

### <a name="manually-creating-a-new-released-product"></a>Ręczne tworzenie nowego zwolnionego produktu

Można ręcznie utworzyć zwolniony produkt w jednej sesji, w zależności od procesów biznesowych stosowanych w organizacji oraz od reguł decydujących o tym, czy tej funkcji należy użyć. Ta funkcja powoduje utworzenie nowego produktu i jego automatyczne zwolnienie do bieżącej firmy. Aby utworzyć nowy produkt, kliknij opcję **Zwolnione produkty** w obszarze roboczym **Obsługa zwolnionego produktu** lub na stronie listy **Zwolniony produkt**.

