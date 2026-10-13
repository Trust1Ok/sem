# Release Notes

## v0.2.0 — Population Reports and DevOps Improvements

19 of 32 report requirements implemented (59.375%).

### Reports

- PB-01: countries in the world by population.
- PB-13 to PB-16: Top N cities by continent, region, country and district.
- PB-17 to PB-19: capital cities by population in the world, a continent and a region.
- PB-20 to PB-22: Top N capital cities in the world, a continent and a region.
- PB-23 to PB-25: population distribution by continent, region and country.
- PB-26: world population.
- PB-27: selected continent population.
- PB-30: selected district population.
- PB-31: selected city population.
- PB-32: five-language population report.

### Process and quality

- MySQL integration tests and coverage reporting (#77).
- GitHub bug-reporting workflow (#75).
- Permanent release route `develop → release → master → develop` (#66, #81).
- Updated use case diagram (#45).

### Verification (2026-10-13)

- `docker build` ran `mvn clean verify` with Java 17: 146 tests, 0 failures.
- Docker Compose with MySQL 8.4.11 and the team's `world.sql` fixture from PB-01
  commit `554f835` (239 countries, 4,079 cities):

```text
PB-01                      CHN | China | Asia | Eastern Asia | 1,277,558,000 | Peking
PB-26                      World | 6,078,749,450
PB-27 Europe               Europe | 730,074,600
PB-30 Scotland             Scotland | 1,429,620
PB-31 Edinburgh            Edinburgh | 450,180
PB-32                      Chinese | 1,191,843,539 | 19.61% (first of 5 rows)
--top-capitals-world 3     Seoul, Jakarta, Ciudad de México
PB-13 Asia 3               Mumbai (Bombay), Seoul, Shanghai
```

## v0.1.0 — Project Foundation

Java 17 Maven application, executable JAR, multi-stage Docker image, Docker Compose environment, GitHub Actions CI, GitFlow branches, team documentation and the product backlog.
