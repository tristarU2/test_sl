docker run --name=internet_parser --network=bridge --restart=always -d amouat/network-utils:latest bash -c "while true; do curl -I slurm.io; sleep 5; done"




"Path": "sh",
        "Args": [
            "-c",
            "while true; do curl -I slurm.io; sleep 5; done"
        ],
