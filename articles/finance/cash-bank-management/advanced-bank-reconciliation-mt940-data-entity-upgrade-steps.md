---
title: Zaawansowane uzgadnianie konta bankowego, import dla formatu MT940 — uaktualnianie złożonej jednostki danych
description: Aby zapewnić obsługę formatu MT940, trzeba dodać numer kolejny do importowanej jednostki wyciągu bankowego.
author: angelad116
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: kfend
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e0cf603e04be4f8f784a32b9ef98d748d4d28e5b
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151500"
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






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
