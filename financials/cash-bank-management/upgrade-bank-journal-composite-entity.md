---
title: "Aktualizowanie jednostki złożonej arkusza bankowego"
description: "Poniższe czynności są niezbędne w celu wstawienia dodatkowego pola BankTransactionType do jednostki złożonej BankJournalEntity."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 43413aad9d537e518f7276ccab11ce01d23cf13f
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="update-the-bank-journal-composite-entity"></a>Aktualizowanie jednostki złożonej arkusza bankowego

[!include[banner](../includes/banner.md)]


Poniższe czynności są niezbędne w celu wstawienia dodatkowego pola BankTransactionType do jednostki złożonej BankJournalEntity.

Poniższa procedura umożliwia wstawienie dodatkowego pola BankTransactionType do jednostki złożonej BankJournalEntity.

1.  Skompiluj i zsynchronizuj następujące jednostki złożone, jednostki i tabele tymczasowe w arkuszu bankowym:
    -   Jednostka złożona\\BankJournalEntity
    -   Jednostka\\BankJournalHeaderEntity
    -   Jednostka\\BankJournalLineEntity
    -   Tabela\\BankJournalHeaderStaging
    -   Tabela\\BankJournalLineStaging

2.  Zarządzanie danymi\\projekty danych
    -   Udostępnij typ **Transakcja bankowa** w układzie **Dane źródłowe**.
        -   Format danych źródłowych = Element XML
        -   Nazwa jednostki = Arkusz bankowy
        -   Przekaż plik danych = nowa wersja pliku SampleBankJournalCompositeEntity.xml.
        -   Kliknij przycisk **Tak**, aby zastąpić istniejący plik.
        -   Kliknij przycisk **Tak**, aby wygenerować mapowanie od zera.
        -   Sprawdź, czy typ transakcji bankowej jest mapowany.
            -   W jednostce Wiersz kliknij opcję **Wyświetl mapę**.
            -   Upewnij się, że typ transakcji bankowej jest mapowany z obszaru Źródło do obszaru Tymczasowy.

3.  Zaimportuj nowy wyciąg.





