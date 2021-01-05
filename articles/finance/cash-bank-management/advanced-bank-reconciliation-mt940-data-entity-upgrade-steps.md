---
title: Zaawansowane uzgadnianie konta bankowego, import dla formatu MT940 — uaktualnianie złożonej jednostki danych
description: Aby zapewnić obsługę formatu MT940, trzeba dodać numer kolejny do importowanej jednostki wyciągu bankowego.
author: panolte
manager: AnnBe
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 65970cdac114b72363d2fbbc08766c99ace00b88
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446739"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>Zaawansowane uzgadnianie konta bankowego, import dla formatu MT940 — uaktualnianie złożonej jednostki danych

[!include [banner](../includes/banner.md)]

Aby zapewnić obsługę formatu MT940, trzeba dodać numer kolejny do importowanej jednostki wyciągu bankowego. 

Poniższa procedura umożliwia dodanie importowanej jednostki wyciągu bankowego w celu obsługi formatu MT940.

1.  Skompiluj i zsynchronizuj następujące elementy:
    -   Jednostka złożona\\BankStatementImportEntity
    -   Jednostka\\BankStatementBalanceEntity
    -   Jednostka\\BankStatementDocumentEntity
    -   Jednostka\\BankStatementEntity
    -   Jednostka\\BankStatementLineEntity
    -   Tabele\\BankStatementStaging

2.  Zarządzanie danymi\\projekty danych.
    1.  Załaduj projekty importu dla formatu MT940
        1.  Zmodyfikuj arkusz stylów XSLT.
            -   Kliknij opcję **Wyświetl mapę**.
            -   Na dokumencie wyciągu bankowego kliknij opcję **Wyświetl mapę**.
            -   Kliknij opcję **Przekształcenia**.
            -   Usuń plik BankReconiliation-to-Composite.xslt.
            -   Dodaj nową wersję pliku BankReconiliation-to-Composite.xsl.

        2.  Udostępnij ustawienie **Numer sekwencyjny** w układzie **Dane źródłowe**.
            1.  Format danych źródłowych = Element XML.
            2.  Nazwa jednostki = Wyciągi bankowe.
            3.  Przekaż plik danych = nowa wersja pliku SampleBankCompositeEntity.xml.
            4.  Kliknij przycisk **Tak**, aby zastąpić istniejący plik.
            5.  Kliknij przycisk **Tak**, aby wygenerować nowe mapowanie.
            6.  Upewnij się, że element **SequenceNumber** jest mapowany.
                -   W jednostce wyciągu kliknij opcję **Wyświetl mapę**.
                -   Upewnij się, że element **SequenceNumber** jest mapowany z obszaru Źródło do obszaru Tymczasowy.

3.  Zaimportuj nowy wyciąg.




