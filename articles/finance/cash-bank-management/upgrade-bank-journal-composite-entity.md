---
title: Aktualizowanie jednostki złożonej arkusza bankowego
description: Poniższe czynności są niezbędne w celu wstawienia dodatkowego pola BankTransactionType do jednostki złożonej BankJournalEntity.
author: ShylaThompson
manager: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 18137ca8cecc43b4269f14b36df2eb8063192e52
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236354"
---
# <a name="update-the-bank-journal-composite-entity"></a>Aktualizowanie jednostki złożonej arkusza bankowego

[!include [banner](../includes/banner.md)]

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






[!INCLUDE[footer-include](../../includes/footer-banner.md)]