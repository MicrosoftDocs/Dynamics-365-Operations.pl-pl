---
title: Aktualizowanie złożonej jednostki arkusza bankowego
description: W tym artykule wymieniono kroki potrzebne do dodania dodatkowego pola BankTransactionType do złożonego BankJournalEntity.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: kfend
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1855f9680ba6bcf8eb46608882a128b4a21f0dac
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715298"
---
# <a name="update-the-bank-journal-composite-entity"></a>Aktualizowanie złożonej jednostki arkusza bankowego

[!include [banner](../includes/banner.md)]

W tym artykule wymieniono kroki potrzebne do dodania dodatkowego pola BankTransactionType do złożonego BankJournalEntity.

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
