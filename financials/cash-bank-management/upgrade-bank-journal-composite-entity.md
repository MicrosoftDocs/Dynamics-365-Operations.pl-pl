---
title: "Aktualizowanie jednostki złożonej arkusza bankowego"
description: "Poniższe czynności są niezbędne w celu wstawienia dodatkowego pola BankTransactionType do jednostki złożonej BankJournalEntity."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer
ms.search.scope: Operations, Core
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 14d58604f5c0aaa4725345f58982387ad0a23205
ms.lasthandoff: 03/31/2017


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





