EXCLUDE_KINDLE := \(電撃文庫\|あすか\|コミックス\|クール教信者\|ファンタジア文庫\|講談社文庫\|MF文庫J\|ファミ通文庫\|限定\|英文法\|プリズナー\|召喚獣\|くがね\|ダンジョン\|FACTFULNESS\|「良い質問」をする技術\|Illustrator\)

.PHONY: kindle
kindle: raw-kindle.csv
	cat raw-kindle.csv | grep -v -E $(EXCLUDE_KINDLE) > kindle.csv

.PHONY: gihyo
gihyo: gihyo.json
	@echo 'Title' > gihyo.csv
	@cat gihyo.json | jq -r '.[]' >> gihyo.csv

.PHONY: tatsu-zine
tatsu-zine: tatsu-zine.json
	@echo 'Title,Authors' > tatsu-zine.csv
	@cat tatsu-zine.json | jq -r '.[]' >> tatsu-zine.csv

.PHONY: booth
booth: booth.json
	@echo 'Title' > booth.csv
	@cat booth.json | jq -r '.[]' >> booth.csv
