---
title: Wypełnianie podstawowych ustawień zwolnionego produktu głównego
description: Ten artykuł opisuje wykonywanie minimalnej konfiguracji, która jest wymagana, zanim produktu głównego będzie można używać w wersjach BOM.
author: t-benebo
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a403600bfdc257587441b5b5a907981d5eebaf58
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844887"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a>Wypełnianie podstawowych ustawień zwolnionego produktu głównego

[!include [banner](../../includes/banner.md)]

Ten artykuł opisuje wykonywanie minimalnej konfiguracji, która jest wymagana, zanim produktu głównego będzie można używać w wersjach BOM.

Jest to trzecia z ośmiu procedur opisujących sposób tworzenia kombinacji dla konfiguracji opartej na wymiarach. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.

1. Otwórz **Okienko nawigacji > Moduły > Informacje o zarządzaniu produktem > Produkty > Wydane produkty**.
2. Na liście znajdź i zaznacz odpowiedni rekord. Wybierz produkt główny, który został zwolniony w drugiej procedurze. Ten produkt główny został utworzona przy użyciu technologii konfiguracji opartej na wymiarach.  
3. W okienku akcji wybierz pozycję **Produkt**.
4. Wybierz **Grupy wymiarów**, aby otworzyć rozwijane okno dialogowe.
5. W polu **Grupa wymiarów magazynowania** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord. Grupa wymiarów magazynowania określa wymiary magazynowania, które są używane dla transakcji produktu. W tej procedurze wybierz opcję **Oddział**.  
7. W polu **Grupa wymiarów śledzenia** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście znajdź i zaznacz odpowiedni rekord. Grupa wymiarów śledzenia określa wymiary śledzenia, które są używane dla transakcji produktu. W tej procedurze wybierz opcję **Brak**.  
9. Kliknij przycisk **OK**.
10. Kliknij przycisk **Edytuj**.
11. W polu **Grupa modeli towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
12. Na liście znajdź i zaznacz odpowiedni rekord. Grupy modeli towarów zawierają ustawienia określające sposób kontroli i obsługi towarów przy ich przyjmowaniu i wydawaniu. Określają one także sposób obliczania zużycia towarów. W tej procedurze wybierz opcję **FIFO**.  
13. Rozwiń sekcję **Zarządzanie kosztami**.
14. W polu **Grupa towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
15. Na liście znajdź i zaznacz odpowiedni rekord. Grupy towarów służą do zarządzania zapasami przez dzielenie towarów magazynowych na grupy. W tej procedurze wybierz opcję **CarAudio**.  
16. W okienku akcji wybierz opcję **Plan**.
17. Wybierz **Ustawienia domyślne zamówienia**.
18. W polu **Domyślny typ zamówienia** wybierz opcję. Wybierz opcję **Produkcja**, aby określić, że domyślną opcja dostaw tego produktu głównego jest jego wytwarzanie.  
19. Wybierz opcję **Zapisz**.
20. Zamknij stronę.
21. Zamknij formularz **Szczegóły zwolnionego produktu**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]