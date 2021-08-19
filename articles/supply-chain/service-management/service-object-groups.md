---
title: Grupy przedmiotów serwisu
description: Grupy przedmiotów serwisu są przydatne do sortowania i filtrowania danych o przedmiotach serwisu do wykorzystania w raportach i statystykach.
author: ShylaThompson
ms.date: 05/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e3a0f70a925bdc249a5f7973be955eaac60ae922830ad9957a6c59a522b6c2f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6715646"
---
# <a name="service-object-groups"></a>Grupy przedmiotów serwisu

[!include [banner](../includes/banner.md)]

Grupy przedmiotów serwisu są przydatne do sortowania i filtrowania danych o przedmiotach serwisu do wykorzystania w raportach i statystykach. Na przykład można grupować obiekty według lokalizacji geograficznej lub według typu.

## <a name="group-by-geographical-location"></a>Grupowanie według lokalizacji geograficznych

Tej metody grupowania można użyć w celu pokazania, gdzie są zlokalizowane różne przedmioty serwisowane przez firmę. Grupowanie przedmiotów serwisu według lokalizacji geograficznych może być również przydatne, jeśli na przykład trzeba wskazać przedmioty, które firma już serwisuje w określonym kraju/regionie.

## <a name="example-of-grouping-by-geographical-location"></a>Przykład grupowania według lokalizacji geograficznych

Klient z Belgii dzwoni do centrum serwisowego i chce zawrzeć umowę serwisową dotyczącą przedmiotu ABC. Grupę przedmiotów serwisu odpowiadającą lokalizacji geograficznej Belgia dołączono do wszystkich obiektów serwisowanych w Belgii. Używając tej grupy jako filtru, można szybko stwierdzić, czy przedmiot ABC już istnieje jako rekord w programie lub czy trzeba skonfigurować nowy przedmiot.

## <a name="group-by-type"></a>Grupowanie według typów

Tej metody grupowania można użyć w celu pokazania typów przedmiotów serwisowanych przez firmę. Grupowanie przedmiotów serwisu według typów może być również przydatne do tworzenia nowych przedmiotów na podstawie podobnych przedmiotów już istniejących w programie.

## <a name="example-of-grouping-by-type"></a>Przykład grupowania według typów

Klient dzwoni w sprawie zawarcia umowy serwisowej dotyczącej urządzenia do klimatyzacji, HIJ. Nie masz jeszcze rekordu dla tej maszyny. Jednak skonfigurowano już grupę przedmiotów serwisu o nazwie Klimatyzatory i dołączono tę grupę do wszystkich przedmiotów związanych z klimatyzacją. W związku z tym można szybko wyszukać i zidentyfikować wszystkie urządzenia do klimatyzacji oraz użyć informacji o tych przedmiotach jako szablonu do utworzenia wierszy umowy serwisowej dotyczącej urządzenia HIJ. Korzystanie z grup przedmiotów w ten sposób pozwala szybko konfigurować nowe przedmioty serwisu i ustalać zadania serwisowe, które trzeba na nich wykonywać.

## <a name="create-service-object-groups"></a>Tworzenie grup przedmiotów serwisu

Można utworzyć grupy, do których będą przypisywane przedmioty serwisu. Przedmioty serwisu są pozycjami magazynowymi i innymi produktami, dla których usługi są wykonywane. Grupowanie przedmiotów serwisu umożliwia tworzenie raportów dotyczących podobnych i powiązanych przedmiotów serwisu. Na przykład, grupa przedmiotów serwisu może składać się z dwóch przedmiotów serwisu: jeden przedmiot serwisu jest zestawem, a drugi przedmiotu serwisu jest usługą montażu zestawu.

Aby utworzyć grupy przedmiotów serwisu, wykonaj następujące czynności:

1. Kliknij kolejno opcje **Zarządzanie serwisem > Ustawienia > Przedmioty serwisu > Grupy przedmiotów serwisu**.

2. Kliknij przycisk **Nowy**, aby utworzyć nową grupę przedmiotów serwisu.

3. Wprowadź niepowtarzalną nazwę grupy przedmiotów serwisu oraz jej opis (opcjonalny).

Przedmioty serwisu można przypisać do grupy za pomocą formularza **Przedmioty serwisu**. 

## <a name="see-also"></a>Informacje dodatkowe

[Tworzenie przedmiotów serwisu](create-service-objects.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]