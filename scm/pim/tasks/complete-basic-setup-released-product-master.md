--- 
title: "Wypełnianie podstawowych ustawień zrealizowanego produktu głównego"
description: "Ta procedura pokazuje wykonywanie minimalnej konfiguracji, która jest wymagana, zanim produktu głównego będzie można używać w wersjach BOM."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 1c7c499b3df92fee5010c731e331e711ea0d1883
ms.contentlocale: pl-pl
ms.lasthandoff: 07/28/2017

---
# <a name="complete-basic-setup-of-a-released-product-master"></a>Wypełnianie podstawowych ustawień zrealizowanego produktu głównego

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje wykonywanie minimalnej konfiguracji, która jest wymagana, zanim produktu głównego będzie można używać w wersjach BOM.

Jest to trzecia z ośmiu procedur opisujących sposób tworzenia kombinacji dla konfiguracji opartej na wymiarach. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.

1. Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz produkt główny, który został zwolniony w drugiej procedurze. Ten produkt główny został utworzona przy użyciu technologii konfiguracji opartej na wymiarach.  
3. W okienku akcji kliknij pozycję Produkt.
4. Kliknij przycisk Grupy wymiarów, aby otworzyć rozwijane okno dialogowe.
5. W polu Grupa wymiarów magazynowania kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
    * Grupa wymiarów magazynowania określa wymiary magazynowania, które są używane dla transakcji produktu. W tej procedurze wybierz opcję Oddział.  
7. Na liście kliknij łącze w wybranym wierszu.
8. W polu Grupa wymiarów śledzenia kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście znajdź i zaznacz odpowiedni rekord.
    * Grupa wymiarów śledzenia określa wymiary śledzenia, które są używane dla transakcji produktu. W tej procedurze wybierz opcję Brak.  
10. Na liście kliknij łącze w wybranym wierszu.
11. Kliknij przycisk OK.
12. Na liście kliknij łącze w wybranym wierszu.
13. Kliknij przycisk Edytuj.
    * Otwórz formularz Szczegóły zwolnionego produktu, aby kontynuować zadanie konfigurowania.  
14. W polu Grupa modeli towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
15. Na liście znajdź i zaznacz odpowiedni rekord.
    * Grupy modeli towarów zawierają ustawienia określające sposób kontroli i obsługi towarów przy ich przyjmowaniu i wydawaniu. Określają one także sposób obliczania zużycia towarów. W tej procedurze wybierz opcję FIFO.  
16. Na liście kliknij łącze w wybranym wierszu.
17. Rozwiń lub zwiń sekcję Zarządzanie kosztami.
18. W polu Grupa towarów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
19. Na liście znajdź i zaznacz odpowiedni rekord.
    * Grupy towarów służą do zarządzania zapasami przez dzielenie towarów magazynowych na grupy. W tej procedurze wybierz opcję CarAudio.  
20. Na liście kliknij łącze w wybranym wierszu.
21. W okienku akcji kliknij opcję Plan.
22. Kliknij opcję Ustawienia domyślne zamówień.
23. W polu Domyślny typ zamówienia wybierz opcję.
    * Wybierz opcję Produkcja, aby określić, że domyślną opcja dostaw tego produktu głównego jest jego wytwarzanie.  
24. Zamknij stronę.
25. Zamknij formularz Szczegóły zwolnionego produktu.

