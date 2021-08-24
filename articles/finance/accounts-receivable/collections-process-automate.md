---
title: Automatyzacja procesu windykacji
description: W tym temacie opisano proces konfigurowania strategii procesu windykacji, która umożliwia automatyczne identyfikowanie faktur odbiorców wymagających przypomnienia w formie wiadomości e-mail, operacji windykacyjnej lub ponagleń wysyłanych do odbiorcy.
author: panolte
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 0afc56ecea72e281d689930cc91cf6048426d3127ab10c8c284b2eea0f3933d6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723902"
---
# <a name="collections-process-automation"></a>Automatyzacja procesu windykacji

[!include [banner](../includes/banner.md)]

W tym temacie opisano proces konfigurowania strategii procesu windykacji, która umożliwia automatyczne identyfikowanie faktur odbiorców wymagających przypomnienia w formie wiadomości e-mail, operacji windykacyjnej (np. rozmowy telefonicznej) lub ponagleń wysyłanych do odbiorcy. 

Organizacje poświęcają znaczne ilości czasu na przeszukiwanie starych faktur, kont odbiorców oraz faktur bieżących, aby określić, z kim należy się kontaktować w sprawie nieopłaconej faktury lub salda konta. Proces ten zabiera wiele czasu, co zmniejsza możliwości pracownika, jeśli chodzi o komunikowanie się z klientami w celu zapłaty zaległych obciążeń lub rozwiązywanie sporów związanych z fakturowaniem. Automatyzacja procesu windykacji pozwala na skonfigurowanie w procesu gromadzenia danych podejścia opartego na strategii. Ułatwia to stosowanie działań windykacyjnych przez udostępnienie dostosowanych przypomnień pocztą e-mail lub zaprogramowanych procesów służących do wysyłania ponagleń. 

## <a name="collections-process-setup"></a>Konfiguracja procesu windykacji
Na stronie **Konfiguracja procesu windykacji** (**Kredyty i windykacja > Konfiguracja > Konfiguracja procesu windykacji**) można utworzyć zautomatyzowany proces windykacji, który będzie planować działania, wysyłać wiadomości e-mail oraz tworzyć i wysyłać listy ponaglające. Etapy procesu są oparte na pierwszej lub najstarszej nieopłaconej fakturze W każdym kroku wykorzystywana jest właśnie ta faktura w celu określenia, jaka komunikacja lub działanie ma być przeprowadzane względem danego klienta.  

Zespoły windykacji zwykle wysyłają wcześniejsze powiadomienie dotyczące każdej zaległej faktury, aby klient był powiadamiany o terminach płatności. Zaznaczenie opcji **Wstępnego duplikowania** można ustawić w taki sposób, aby zezwolić na działanie jednego kroku w każdej hierarchii procesów dla każdej faktury w czasie, do osiągnięcia tego etapu.

### <a name="process-hierarchy"></a>Hierarchia procesów
Każda pula klientów może być przypisana tylko do jednej hierarchii procesów. Ranga hierarchii w tym kroku określa, który proces będzie miał pierwszeństwo, jeśli klient zostanie uwzględniony w więcej niż jednej puli z przypisaną hierarchią procesów. Identyfikator puli określa, którzy klienci będą przypisani do procesu. 

Funkcja „Dni bez kontaktu” służy do zapewnienia, że automatyczny kontakt z danym klientem nie będzie miał miejsca zbyt często.  Jeśli na przykład wartość w funkcji „Dni bez kontaktu” wynosi dwa, odbiorca nie będzie kontaktowany przez proces zautomatyzowany przez co najmniej dwa dni, nawet jeśli oryginalna faktura wiodąca zostanie rozliczona w całości. 

Aby wykluczyć jakichś odbiorców z automatyzacji procesu, jeśli saldo konta lub saldo faktury są niższe od określonej wartości, w polu **Wyklucz z procesu** wybierz wartość **Tak** i wprowadź wartość kwoty.

## <a name="process-details"></a>Szczegóły procesu
**Opis** służy do identyfikowania celu lub nazwy etapu w hierarchii.

**Typ akcji** określa, czy etap ma utworzyć działanie, wysłać wiadomość e-mail lub utworzyć ponaglenie.

**Dokument biznesowy** określa szablon używany do tworzenia typu akcji.  Może to być szablon działania, szablon wiadomości e-mail lub ponaglenie dla odbiorcy. 

Typy akcji można tworzyć przed datą płatności faktury lub po niej, na podstawie ustawienia wyświetlonego w kolumnie **Dni w odniesieniu do daty płatności faktury**.

Po wybraniu typu działania — wiadomość e-mail pole adresat będzie używane do określenia, czy wiadomość wysyłana jest do klienta, grupy sprzedażowej czy do agenta windykacji. Wartość pola **Kontakt w celach biznesowych** określa, który kontakt z konta danego odbiorcy będzie otrzymywał wiadomości.

## <a name="business-document-details"></a>Szczegóły dokumentacji biznesowej
Szczegóły dokumentu biznesowego różnią się w zależności od typu działania wybranego w szczegółach procesu.  Jeśli typem akcji jest działanie, zostaną wyświetlone szczegóły szablonu działania.  Do tych szczegółów należą nazwa szablonu działania, typ działania, które zostanie utworzone, cel działania, liczba dni zaplanowanych do zakończenia działania oraz szczegóły działania.  To działanie następnie przekieruje odbiorcę do faktury wiodącej, która informuje go o wymaganym działaniu.

Jeśli w szczegółach procesu typem akcji jest wiadomość e-mail, ta sekcja będzie zawierać dwie skrócone karty.  Pierwsza służy do określenia identyfikatora szablonu, opisu wiadomości e-mail, domyślnego języka, nazwy użytkownika, która zostanie przypisana do wysyłanych automatycznie wiadomości e-mail oraz skojarzonych z nią adresów e-mail nadawców. Druga umożliwi utworzenie treści wiadomości e-mail po zapisaniu wartości w polach **Język** i **Temat** przez wybranie opcji **Edytuj**.  Spowoduje to otwarcie okna umożliwiającego przesyłanie zawartości HTML. Można również wpisać wiadomość utworzoną ręcznie w lewym dolnym polu okna.  

> [!Note]
> Wiadomość e-mail programu Outlook może być zapisana z żądaną treścią w formacie HTML. Można ją następnie przesłać w celu wdrożenia szablonu. <br> <br> W przypadku wybrania typu akcji ponaglenie, w formularzu ustawień nie pojawi się sekcja szczegółów dokumentu biznesowego.


## <a name="fasttab-reference"></a>Odwołanie do skróconej karty
W poniższych tabelach przedstawiono strony i pola, z których można uzyskać dostęp do określonych skróconych kart wraz z opisem informacji znajdujących się na danej karcie. 

### <a name="process-hierarchy"></a>Hierarchia procesów

|     Strona                                                  |     Pole                         |     opis                           |
| --------------------------------------------------------  |-------------------------------    |---------------------------------------    |
|     Konfiguracja procesu windykacji <br> Automatyzacja procesu       |                                   |     Umożliwia tworzenie procesów windykacji na podstawie przypisań puli odbiorców i zarządzanie nimi.                                                                                                                             |
|     Konfiguracja procesu windykacji <br> Automatyzacja procesu       |     Hierarchia                     |     Określa priorytet automatyzacji procesu w celu przypisania odbiorcy, jeśli należy on do wielu pul.                                                                                                   |
|     Konfiguracja procesu windykacji <br> Automatyzacja procesu       |     Identyfikator puli                       |     Kwerendy definiujące grupę rekordów odbiorców.                                                                                                                                                        |
|     Konfiguracja procesu windykacji <br> Automatyzacja procesu       |     Ciche dni                    |     Umożliwia ograniczenie częstotliwości wykonywania etapu procesu. Na przykład, jeśli w polu „Brak kontaktu” wybrano wartość 2 dni, kolejne kroki procesu nie będą wykonywane przez co najmniej dwa dni, jeśli zostanie zmieniona początkowa faktura.     |
|     Konfiguracja procesu windykacji <br> Automatyzacja procesu       |     Wyklucz z procesu        |     Wybranie opcji **Saldo wiekowania odbiorcy mniejsze niż** lub **Kwoty na fakturze mniejsze niż** spowoduje wykluczenie odbiorcy z automatyzacji procesu, jeśli nie zostaną spełnione kryteria dotyczące wartości.                                   |

### <a name="process-details"></a>Szczegóły procesu
|     Strona                                                  |     Pole                                         |      opis                  |
|--------------------------------------------------------   |-----------------------------------------------    |----------------------------   |
|     Konfiguracja procesu windykacji <br> Automatyzacja procesu       |                                                   |     Umożliwia zdefiniowanie kroków wykonanych na podstawie faktury wiodącej.                                                                                                |
|                                                           |     opis                                   |     Pole „tekst niezależny” służy do podawania nazwy i/lub opisu kroku.                                                                           |
|                                                           |     Typ akcji                                   |     Działania, wiadomości e-mail lub ponaglenia, które zostaną utworzone przez krok procesu.                                                                     |
|                                                           |     Dokument biznesowy                           |     Definiuje działanie lub szablon wiadomości e-mail, który jest używany w kroku procesu.                                                                        |
|                                                           |     Kiedy                                          |     Określa, czy krok procesu ma nastąpić przed upływem terminu faktury, czy w dniu poprzedzającym ten termin, wspólnie z informacjami w polu **Dni w odniesieniu do daty płatności faktury**.        |
|                                                           |     Dni w odniesieniu do daty płatności faktury        |     Wraz z polem **Kiedy** określa czas etapu procesu.                                                                          |
|                                                           |     Wstępne monitowanie                                   |     Ten wybór pozwoli na ustawienie jednego kroku na hierarchię procesów i uruchamianie ich w stosunku do każdej faktury, która spełnia kryteria dotyczące czasu.                                                |
|                                                           |     Odbiorca                                     |     Określa, czy wiadomość e-mail zostanie wysłana do klienta, grupy sprzedaży lub agenta windykacji.                                                   |
|                                                           |     Kontakt w celach biznesowych                    |     Określa, który adres e-mail adresata jest używany w komunikacji e-mail.                                                                                 |

### <a name="business-process-activity-template-details"></a>Szczegóły szablonu działań w procesie biznesowym 
|     Strona                                                  |     Pole                     |      opis                  |
|--------------------------------------------------------   |----------------------------   |-------------------------  |
|     Konfiguracja procesu windykacji <br> Automatyzacja procesu       |                               |     Sekcja procesu konfiguracji, która identyfikuje szczegóły szablonu działania.                                                                      |
|     Konfiguracja procesu windykacji <br> Automatyzacja procesu       |     Szablon działania       |     Określa typ, cel, liczbę dni do zakończenia i zawiera szczegóły dotyczące działania, które zostanie utworzone podczas etapu procesu działania.       |

### <a name="business-document-email-template-details"></a>Szczegóły szablonu wiadomości e-mail dotyczącej dokumentów biznesowych 
|     Strona                                                  |     Pole     |      opis                  |
|--------------------------------------------------------   |-------------- |-----------------------------  |
|     Konfiguracja procesu windykacji <br> Automatyzacja procesu       |               |     Określa opis wiadomości e-mail, domyślny język, nazwę nadawcy i adres e-mail, które zostaną utworzone podczas etapu procesu wiadomości e-mail.        |


### <a name="collections-history"></a>Historia windykacji 
|     Strona                              |     Pole     |      opis                                                          |
|------------------------------------   |-------------- |---------------------------------------------------------------------  |
|     Konfiguracja procesu windykacji       |               |     Służy do wyświetlania najnowszej historii dla wybranej hierarchii procesów.       |

### <a name="collection-process-assignment"></a>Przydzielanie procesu windykacji
|     Strona                              |     Pole     |      opis                                                  |
|------------------------------------   |-------------- |-----------------------------------------------------------    |
|     Konfiguracja procesu windykacji       |               |     Umożliwia wyświetlenie odbiorców przypisanych do procesu windykacji.  
|     Przypisanie ręczne               |               |     Umożliwia wyświetlenie odbiorców ręcznie przypisanych do danego procesu lub wybranie opcji odbiorcy, którzy mają być przypisani do procesu. |
|     Podgląd przypisania procesu      |               |     Umożliwia wyświetlenie podglądu odbiorców, którzy zostaną przypisani do strategii po jej uruchomieniu.   |
|     Podgląd przypisania odbiorcy     |               |     Służy do wyświetlania strategii przypisanej do określonego odbiorcy.    |
 
 ### <a name="process-simulation"></a>Przetwórz symulację
|     Strona                              |     Pole     |      opis                                                  |
|------------------------------------   |-------------- |-----------------------------------------------------------    |
|    Przetwórz symulację                 |               |     Umożliwia podgląd akcji, które zostaną utworzone, jeśli w tej chwili zostanie uruchomione wybrane automatyzacja procesów. |

### <a name="parameters"></a>Parametry
|     Strona                                                                  |     Pole                                             |      opis                              |
|-------------------------------------------------------------------------- |------------------------------------------------------ |-------------------------------------  |
|     Parametry modułu rozrachunków z odbiorcami > Automatyzacja procesu windykacji     |     Procent odbiorców na zadanie wsadowe          |     Ustawienie określające liczbę zadań wsadowych na każdy proces automatyzacji.                                          |
|     Parametry modułu rozrachunków z odbiorcami > Automatyzacja procesu windykacji     |     Automatycznie wysyłaj ponaglenia           |     Typy akcji ponagleń spowodują wysłanie listu podczas automatyzacji.                                      |
|     Parametry modułu rozrachunków z odbiorcami > Automatyzacja procesu windykacji     |     Tworzenie działań na potrzeby automatyzacji                |     Służy do tworzenia i zamykania działań dla typów akcji niezwiązanych z działaniami w celu wyświetlenia wszystkich zautomatyzowanych kroków podjętych na koncie.        |
|     Parametry modułu rozrachunków z odbiorcami > Automatyzacja procesu windykacji     |     Dni do przechowywania automatyzacji procesu windykacji     |     Definiuje liczbę dni przechowywania historii windykacji.                                                       |
|     Parametry modułu rozrachunków z odbiorcami > Automatyzacja procesu windykacji     |     Wyklucz fakturę po aktywowaniu ostatniego kroku procesu    |     Faktura, która dotrę do ostatniego kroku procesu windykacji, nie będzie używana do tworzenia przyszłych typów akcji automatyzacji procesów. Następna najstarsza faktura określi następny krok automatyzacji procesu, aby zapewnić kontynuację akcji automatyzacji procesów windykacji.                                                        |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
