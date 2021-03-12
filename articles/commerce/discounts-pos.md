---
title: Wyświetl rabaty w punkcie sprzedaży
description: W tym temacie wyjaśniono, w jaki sposób Microsoft Dynamics 365 Commerce pomaga współpracownikom ds. sprzedaży dowiedzieć się o promocjach i sposobach ich wykorzystania do sprzedaży krzyżowej i dodatkowej.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 07/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-Commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-02-28
ms.dyn365.ops.version: Application update 10.0.10
ms.openlocfilehash: 118e7689e5d37aae18d3823b957301ddfa89369a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982648"
---
# <a name="show-discounts-in-pos"></a>Wyświetl rabaty w punkcie sprzedaży

[!include [banner](includes/banner.md)]

Promocje odgrywają ważną rolę w motywach klientów, którzy podejmują decyzje dotyczące kupowania. Na przykład święta mogą wyprodukować najwyższą liczbę sprzedaży detalicznych, ponieważ cały rynek detaliczny jest zalewany za pomocą zachęcających promocji i rabatów. Jeśli pracownicy sklepu mają dostęp i rozumieją informacje o dostępnych promocjach, mogą oni łatwo korzystać z tych promocji w celu sprzedaży krzyżowej i dodatkowej towarów. W tym temacie wyjaśniono, w jaki sposób Microsoft Dynamics 365 Commerce pomaga współpracownikom ds. sprzedaży dowiedzieć się o promocjach i sposobach ich wykorzystania do sprzedaży krzyżowej i dodatkowej.

## <a name="learn-about-store-discounts"></a>Dowiedz się więcej o rabatach sklepowych

Commerce zawiera operację o nazwie „Wyświetl wszystkie rabaty”. Ta operacja umożliwia wyświetlenie wszystkich rabatów, które są obecnie uruchomione w sklepie. Operację „Wyświetl wszystkie rabaty” można zamapować na przycisk w punkt sprzedaży (POS), a ten przycisk można dodać do strony **powitalnej** lub do strony **transakcji**. Na poniższej ilustracji pokazano przykład otwartej strony **Wszystkie rabaty**.

![Strona wszystkich rabatów](./media/View_all_discounts.png "Strona wszystkich rabatów")

Aby wyświetlić rabaty, system wyszuka wszystkie rabaty spełniające co najmniej jeden z następujących warunków:

- Grupa cenowa rabatu jest zgodna z grupą cenową sklepu.
- Grupa cenowa rabatu jest zamapowana na przynależność lub do programu lojalnościowego.
- Grupa cenowa rabatu jest zamapowana na katalog skojarzony z danym sklepem.

Na stronie **wszystkie rabaty** są wyświetlane tylko niektóre zniżki kuponów, ponieważ sprzedawcy detaliczni zwykle tworzą tysiące kuponów i odpowiadające im rabaty dla unikatowych odbiorców, a ta strona nie ma na celu wyświetlania rabatów właściwych dla odbiorcy. Rabaty oparte na kuponach są wyświetlane tylko wtedy, gdy w każdym nagłówku kuponu jest włączona opcja **Zastosuj bez kodu kuponu**. W takim przypadku kasjerzy mogą stosować kupon bez konieczności wprowadzania lub skanowania kodu kuponu i kodu kreskowego.

Jeśli opcja **Zastosuj bez kodu kuponu** jest włączona, dostępne są różne scenariusze. Na przykład kasjerzy mogą przydzielać klientom dodatkowe rabaty na potrzeby zaspokojenia odbiorców lub z powodu wad produktu. Wydrukowane kody kuponów i kody kreskowe nie muszą być dystrybuowane do kasjerów. Zamiast tego Kasjer może wybrać przycisk **Zastosuj kupon**. Następnie kupon zostanie automatycznie zastosowany do transakcji. Jeśli istnieje wiele kuponów dla nagłówka kuponu, system automatycznie wybiera pierwsze aktywne kupony transakcji.

Na stronie **wszystkie rabaty** sprzedawcy mogą również przeszukiwać rabaty według słów kluczowych. Wyszukiwanie słów kluczowych wyszukuje w polach, w których jest przechowywana nazwa rabatu i opis rabatu. Sprzedawcy mogą również filtrować rabaty na podstawie tego, czy rabat wymaga kodu kuponu.

## <a name="cross-sell-and-upsell-by-using-discounts"></a>Sprzedaż krzyżowa i dodatkowa przy użyciu rabatów

Rabaty wspólne, takie jak rabaty ilościowe, rabaty za skład zamówienia oraz rabaty progowe, to świetny sposób na zwiększenie atrakcyjności dla odbiorców w celu zakupu większej liczby produktów w celu uzyskania większych rabatów. Dzięki temu zwiększa się także rozmiar koszyka odbiorcy i przychodu sprzedawcy detalicznego. Te rabaty można wystawić na stronach sieci handlu elektronicznego, na nośnikach społecznościowych i na transparentach w sklepie.

Jednak nawet jeśli są używane wszystkie te metody reklamowe, odbiorcy mogą przegapić szansę skorzystania z promocji. Aby pracownicy ds. sprzedaży mogli łatwiej identyfikować, jakie promocje mają zastosowanie do wybranego wiersza, a nawet do całego koszyka, detaliści mogą dodać przycisk dla operacji **„Wyświetl dostępne rabaty”** do dowolnej siatki przycisków na stronie **Transakcja**. W rezultacie pracownik ds. sprzedaży może wybrać wiersz transakcji, a następnie wybrać przycisk, aby wyświetlić wszystkie rabaty dostępne dla wybranego wiersza. Sprzedawca może również wybrać inną kartę, aby wyświetlić rabaty dotyczące całej transakcji. Należy pamiętać, że w **Wyświetl dostępne rabaty** nie są wyświetlane rabaty, które zostały już zastosowane w wierszu sprzedaży, ponieważ informacje o rabatach są już widoczne w wierszu sprzedaży. Celem tego scenariusza jest wyświetlenie tylko tych rabatów, które nie zostały jeszcze zastosowane. Wyjątkiem jest rabaty stosowane na podstawie kuponu oznaczonego jako „Zastosuj bez kodu kuponu”. Ułatwia to, aby sprzedaż była powiązana z łatwym usuwaniem kuponu, który je zastosował.

Strona **Wszystkie rabaty** zawiera tylko rabaty, które nie konkurują z żadnymi zastosowanymi rabatami. To zachowanie pomaga zagwarantować, że jeśli sprzedawca poinformuje klienta o rabacie, a klient podejmie wymaganą akcję (np. klient kupuje jeszcze jedną pozycję, aby uzyskać 10% rabatu), rabat zostanie zastosowany do transakcji. Rabaty oparte na kuponach są wyświetlane tylko po włączeniu opcji **Zastosuj bez kodu kuponu**.

W prostym scenariuszu, w którym wszystkie rabaty mają ten sam priorytet, tryb współbieżności rabatu jest **składany**, a kontrola współbieżności rabatu jest ustawiana na **najlepszą cenę i związek z priorytetem, nigdy nie stanowią związku między priorytetami**, na stronie **wszystkie rabaty** są wyświetlane wszystkie dostępne rabaty dla produktu, ponieważ wszystkie rabaty są złożone i nie konkurują ze sobą nawzajem.

Na poniższych ilustracjach przedstawiono logikę, która określa, które rabaty są wyświetlane w zaawansowanych scenariuszach, na przykład scenariusz, w którym tryb współbieżności rabatu to **Najlepsza cena** lub **wyłączny** oraz są używane dwa lub więcej priorytety. W tych scenariuszach w zależności od tego, czy kontrola współbieżności rabatu jest ustawiona na **najlepszą cenę związaną z priorytetem, bez związku między priorytetami** lub **Najlepszą cenę tylko w ramach priorytetu, zawsze związaną między priorytetami**.

Na poniższej ilustracji przedstawiono logikę, która jest używana w przypadku, gdy kontrola współbieżności rabatu jest ustawiona na **najlepszą cenę i związek z priorytetem, a nie związek między priorytetami**.

![Logika dla najlepszej ceny i związku w ramach priorytetu, nigdy nie związane między priorytetami](./media/Model_1.png "Logika dla najlepszej ceny i związku w ramach priorytetu, nigdy nie związane między priorytetami")

Na poniższej ilustracji przedstawiono logikę, która jest używana w przypadku, gdy kontrola współbieżności rabatu jest ustawiona na **najlepszą cenę tylko w ramach priorytetu, zawsze w ramach związku między priorytetami**.

![Logika dla najlepszej ceny tylko w ramach priorytetu, zawsze w ramach związku między priorytetami](./media/Model_2.png "Logika dla najlepszej ceny tylko w ramach priorytetu, zawsze w ramach związku między priorytetami")
