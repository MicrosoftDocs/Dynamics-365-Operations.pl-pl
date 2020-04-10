---
title: Przeniesienie budżetów projektu na koniec roku obrachunkowego
description: W tym artykule zamieszczono informacje dotyczące sposobu przenoszenia pozostałych kwot budżetu do przyszłych lat i utworzenia szczegółów rejestru budżetu.
author: RadhikaRS
manager: AnnBe
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 41e985825a24de2d6510938cf3d61715c35f9939
ms.sourcegitcommit: 2ea5ff784500d5be9203e9a1560eabd4fea46f4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172337"
---
# <a name="transfer-project-budgets-at-fiscal-year-end"></a>Przeniesienie budżetów projektu na koniec roku obrachunkowego

[!include [banner](../includes/banner.md)]

Podczas pracy w projekcie wieloletnim może być pozostały budżet na koniec roku obrachunkowego. Możesz przenieść pozostałe kwoty budżetu na przyszły rok i utworzyć szczegóły rejestru budżetu dla kwot na powiązanych kontach księgi głównej. Przed przeniesieniem pozostałych kwot pzejrzyj i przeanalizuj pozostałe kwoty budżetu.

## <a name="review-and-analyze-remaining-budget-amounts"></a>Przegląd i analiza pozostałych kwot budżetu

Wykonanie następujących kroków umożliwia przeglądanie na koniec roku kwot budżetu dla projektów, które jednak nie mają przeniesienia na następny okres.

1. Przejdź do obszaru **Zarządzanie projektami i ich księgowanie** > **Okresowe** > **Budżety** > **Przeniesione budżety**. 
2. Na stronie **Proces przenoszenia budżetu projektu** na karcie **Opcje na koniec roku** wprawdź, czy **Przeniesione kwoty budżetu projektu na następny okres** nie są włączone.
3. Na karcie **Parametery** w polu **Rok budżetu projektu** wybierz rok obrachunkowy, dla którego chcesz wyświetlić pozostałe kwoty budżetu. 
4. W polu **Otwarcie roku obrachunkowego** wybierz rok obrachunkowy, dla którego chcesz wyświetlić pozostałe kwoty budżetu. 
5. W polu **Od modelu prognozy** wybierz opcję **Pozostały budżet**. 
6. Aby uwzględnić projekty spełniające wybrane kryteria i nie pozostały budżet, wybierz opcję **Pokaż z wyczerpanym budżetem**.  
7. Na karcie **Wybór budżetów** wybierz opcję **Pobierz wszystkie budżety**, aby załadować wszystkie budżety spełniające wybrane kryteria, a następnie wybierz opcję **Przetwórz**. 
8. Aby zaprojektować zapytanie do bazy danych, które ładuje określony zestaw budżetów do okienka, wybierz **Pobierz wybrane budżety**.

Aby uzyskać więcej informacji dotyczących określonego wiersza w okienku, zaznacz wiersz, a następnie wybierz opcję **Wyświetl szczegóły budżetu** lub **Wyświetl konta**.

## <a name="carry-forward-remaining-budget-amounts"></a>Przenieś na następny okres niewykorzystane kwoty budżetu 

Podczas przetwarzania pozostałych kwot budżetu możesz utworzyć transakcje w księdze głównej dla kwot, które zostały przeniesione na następny okres. Aby utworzyć transakcje księgi głównej, należy wykonać kroki opisane w sekcji, [przenieść kwoty budżetu na następny okres i utworzyć transakcje księgi głównej](#carry-forward). 

> [!NOTE]
> Kwoty budżetu, które zostały przeniesione na następny okres są transferowane do modelu prognozy wybranego na stronie **Modele prognoz** jako przeniesienie na następny okres.  

## <a name="carry-forward-budget-amounts-and-create-general-ledger-transactions"></a><a name="carry-forward"></a>Przenoszenie kwot budżetu na późniejszy okres i tworzenie transakcji księgi głównej

1.  Przejdź do obszaru **Zarządzanie projektami i ich księgowanie** > **Okresowe** > **Budżety** > **Przeniesione budżety**. 
2. Na stronie **Proces przeniesienia budżetu projektu**, wybierz opcję **Koniec roku**, a następnie włącz **Przenieś na następny okres niewykorzystane kwoty budżetu projektu** i **Utwórz wpisy do rejestru budżetu w księdze głównej**. 
3. Na karcie **Parametry** w grupie pól **Parametry projektu** wybierz następujące opcje:

   - **Rok budżetu projektu**: wybierz początek roku obrachunkowego, dla którego chcesz wyświetlić pozostałe kwoty budżetu. 
   - **Wynikowe**: utwórz transakcje wynikowe w księdze głównej. 
   -  **PWT**: umożliwia tworzenie transakcji pracy w toku (PWT) w księdze głównej.
   -  **Lista płac**: utwórz transakcje alokacji płac w księdze głównej. 

5. Podaj następujące informacje w grupie pól w **Księdze głównej**: 

   - W polu **Otwarcie roku obrachunkowego** wybierz rok obrachunkowy, do którego chcesz przenieść pozostałe kwoty budżetu dla projektów. Wartość domyślna to jeden rok po wartości pola **Rok budżetu projektu**.
   -  W polu **Okres przeniesienia** wybierz okres, w którym chcesz utworzyć szczegóły rejestru budżetu w księdze głównej. Zwykle jest to pierwszy okres w roku obrachunkowym otwarcia.

6. Podaj następujące informacje w grupie pól **Kopiuj od/do**:

   - W polu **Od modelu prognozy** wybierz model prognozy budżetu projektu, który jest skojarzony z pozostałymi kwotami budżetu, które chcesz transferować dla projektów. 
   - W polu **Do modelu budżetu księgi** wybierz model budżetu księgi, który jest skojarzony z kwotami budżetu, które chcesz transferować do księgi głównej. 
   -  Wybierz **Przenieś walutę sprzedaży**, aby używać waluty sprzedaży projektu dla transakcji księgi głównej tworzonych podczas przenoszenia kwot budżetu dla projektów. Jeśli opcja nie jest zaznaczona, w transakcjach jest używana waluta rozliczeniowa. 
   -  Wybierz **Pokaż z wyczerpanym budżetem**, aby uwzględnić w ramach projektów, które są wyświetlane w okienku u dołu formularza projekty, które nie mają żadnych pozostałych kwot budżetu, lecz spełniają inne kryteria, które wybrałeś w wyświetlonych w dolnym okienku projektach.

7. Na karcie **Wybór budżetów** wybierz opcję **Pobierz wszystkie budżety**, aby załadować wszystkie budżety spełniające wybrane kryteria. Jeśli wolisz zaprojektować zapytanie do bazy danych, które ładuje określony zestaw budżetów do okienka, wybierz **Pobierz wybrane budżety**.
8. Dla poszczególnych projektów, które mają zostać przetworzone, zaznacz opcję na początku wiersza dla projektu.

    > [!TIP]
    > Aby zaznaczyć wszystkie lub większość projektów, zaznacz pole wyboru w górnym lewym rogu. Aby wykluczyć przetwarzanie dowolnego projektu, wyczyść znacznik wyboru w tym projekcie.

9. Aby przenieść pozostałe kwoty budżetu dla wybranych projektów do wybranego roku obrachunkowego i tworzyć szczegóły rejestru budżetu w księdze głównej, wybierz **Przetwórz**.

## <a name="carry-forward-budget-amounts-without-creating-general-ledger-transactions"></a>Przenoszenie kwot budżetu na późniejszy okres bez tworzenia transakcji księgi głównej

1. Przejdź do obszaru **Zarządzanie projektami i ich księgowanie** > **Okresowe** > **Budżety** > **Przeniesione budżety**.
2. Na stronie **Proces przenoszenia budżetu projektu** w polu **Opcje na koniec roku** wybierz **Przeniesione kwoty budżetu projektu na następny okres**.
3. W grupie **Parametery** w polu **Rok budżetu projektu** wybierz rok obrachunkowy, dla którego chcesz wyświetlić pozostałe kwoty budżetu.
4. Podaj następujące informacje w grupie **Kopiuj od/do**:

   - W polu **Od modelu prognozy** wybierz model prognozy budżetu projektu, który jest skojarzony z pozostałymi kwotami budżetu, które chcesz transferować dla projektów. 
   - Wybierz opcję **Pokaż z wyczerpanym budżetem**, aby uwzględnić projekty, które nie mają pozostałych kwot budżetu, ale spełniają inne wybrane kryteria.
   - W grupie **Wybór budżetów** wybierz opcję **Pobierz wszystkie budżety**, aby załadować wszystkie budżety spełniające wybrane kryteria. Aby zaprojektować zapytanie do bazy danych, które ładuje określony zestaw budżetów projektów do okienka, wybierz **Pobierz wybrane budżety**.

5. Dla poszczególnych projektów, które mają zostać przetworzone, zaznacz opcję na początku wiersza dla projektu. 
6. Wybierz **Przetwórz**, aby przenieść pozostałe kwoty budżetu dla wybranych projektów do wybranego roku obrachunkowego.

