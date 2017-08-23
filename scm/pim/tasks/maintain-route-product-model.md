--- 
title: "Obsługa marszruty dla modelu produktu"
description: Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.
author: BibiSp
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 3f6bacc54664c32a7d42f2befc51c420e29ada56
ms.contentlocale: pl-pl
ms.lasthandoff: 07/28/2017

---
# <a name="maintain-a-route-for-a-product-model"></a>Obsługa marszruty dla modelu produktu

[!include[task guide banner](../../includes/task-guide-banner.md)]

Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu. Ta procedura wykorzystuje w kolejnych krokach model Głośnik o wysokiej jakości zdefiniowany w firmie demonstracyjnej USMF.


## <a name="add-a-route-operation"></a>Dodawanie operacji marszruty
1. Kliknij opcję Definicja modelu wariantu produktu.
2. Kliknij opcję Modele konfiguracji produktu.
3. Na liście znajdź i zaznacz odpowiedni rekord.
    * Do tego ćwiczenia wybierz model Głośnik o wysokiej jakości.  
4. Na liście kliknij łącze w wybranym wierszu.
5. Rozwiń sekcję Operacje marszruty.
6. Kliknij przycisk Dodaj.
7. W polu Nazwa wpisz wartość.
8. Wypełnij pole Opis.
9. Kliknij przycisk Zapisz.

## <a name="enter-route-operation-details"></a>Wprowadzanie szczegółów operacji marszruty
1. Kliknij opcję Szczegóły operacji marszruty.
2. W polu Operacja wprowadź lub wybierz wartość.
3. W polu Nr operacji Nr wpisz liczbę.
    * Numery operacji decydują o kolejności czynności w marszrucie.  
    * Każda właściwość operacji marszruty może przybierać wartość statyczną lub być zmapowana do atrybutu. Mapowanie do atrybutu spowoduje ustawianie wartość w trakcie konfigurowania.  
4. W polu Grupa marszruty wpisz lub wprowadź wartość.
    * Grupa marszrut określa podstawowe zachowania dotyczące wyceny, zużycia i konfiguracji.  
5. Kliknij kartę Ustawienia.
6. Kliknij kartę Czasy.
7. W polu Ilość z procesu wpisz liczbę.
    * Określ, ile będzie przetwarzanych w jednej operacji.  
8. W polu Godziny/czas wpisz liczbę.
    * Wprowadź współczynnik czasu.  
9. Zaznacz pole wyboru Ustaw.
10. W polu Czas procesu wpisz liczbę.
    * Określ czas przetwarzania dla podanej ilości.  
11. Kliknij kartę Zapotrzebowanie na zasoby.
12. Kliknij przycisk Dodaj.
13. Na liście oznacz wybrany wiersz.
14. W polu Typ wymagania wybierz opcję.
    * Zdecyduj, czy chcesz określić konkretne zasoby czy możliwości, które muszą posiadać.  
15. W polu Zapotrzebowanie wprowadź lub wybierz wartość.
16. Kliknij przycisk OK.


