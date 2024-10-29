# Microservices Architecture

This project utilizes the following components:

- API Gateway
- Config Server
- Discovery Server
- Student Microservice
- School Microservice
- OpenFeign for inter-service communication
- Distributed Tracing with Zipkin

                            +-----------------+
                            |     Client      |
                            +--------+--------+
                                     |
                                     v
                            +-----------------+
                            |   API Gateway    |
                            +--------+--------+
                                     |
                                     v
                            +-----------------+
                            |  Discovery      |
                            |     Server      |
                            +--------+--------+
                                     |
                       +-------------+-------------+
                       |                           |
                       v                           v
            +------------------+       +------------------------+
            |   Config Server   |      |  Student Microservice  |
            +------------------+       +------------------------+
                                                    |    ^
                                                    |    |
                                                    |    |  OpenFeign
                                                    |    |
                                                    v    |
                                                +----------------------+
                                                |  School Microservice |
                                                +----------------------+
                                                        ^
                                                        |
                                                        |  Zipkin for Distributed Tracing
                                                        |
                                                        v
                                                +-----------------+
                                                |      Zipkin      |
                                                +-----------------+


